pipeline {
    agent any 

    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'ARTIFACT_NAME', value: '$.artifactory.webhook.data.name'],
                [key: 'EVENT_NAME', value: '$.artifactory.webhook.event']
            ],
            causeString: 'Triggered on $ARTIFACT_NAME',
            regexpFilterText: '$EVENT_NAME-$ARTIFACT_NAME',
            regexpFilterExpression: 'storage\.afterCreate-SuperPackage'
        )
    }

    stages {
        stage("Config") {
            steps {
                echo "Configuring pipeline one..."
            }
        }
        stage("Build") {
            steps {
                echo "Building pipeline one..."
            }
        }
    }
}