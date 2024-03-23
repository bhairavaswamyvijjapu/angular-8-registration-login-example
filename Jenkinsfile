@Library(value='jenkins-pipeline-library@npm', changelog=false) _
   

// Pipeline supported branches names pattern:
// dev
// develop
// master
// Release/*/dev
// Release/*/master

// variables map is needed for pipeline execution, global parameters are set as environment variables by default,
// local parameters are set based on a condition described in mainFrontend method

// VERSION varibale is used to tag dockerimage in ECR,
// for dev and Release/*/dev development VERSION will be used hence image will be pushed with SNAPSHOT tag 
// for builds from master or Release/*/master branches release VERSION will be used, tag will be pushed accoring to the variable

def variablesMap = [
    global: [
        'REGION_NAME': 'us-east-1',
        'APP_NAME': 'frontend-HipWebPlannerUI'

        
    ],  
    local: [
        dev: [
            'VERSION'         : '01.00',
            'AWS_UI_S3_BUCKET': 'hipwebplannerui',
            'PARAMETER_NAME'  : '/hpop-dev/hipwebplannerui-service_dev/version'
        ],
        main: [
            'VERSION'         : '01.00',
            'AWS_UI_S3_BUCKET': 'stagging-hipwebplannerui',
            'PARAMETER_NAME'  : '/hpop-test/hipwebplannerui-service_test/version'
        ]
    ]
]

mainHipFrontend(variablesMap)
