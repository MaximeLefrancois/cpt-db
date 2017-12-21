node {

	parameters {
        string(name: 'ENV', defaultValue: 'develop', description: 'Quel environnement de deploiement?')
    }
	
	stage("Récupération des sources") {
		checkout scm
	}

	stage("Deploiement de l'application Db") {
		sh "echo APPLICATION-DB"
	}
	
	if (params.ENV == 'master') {
		stage("Deploiement de l'application Back en prod") {
			sh "echo APPLICATION-BACK"
		}
	}
	
	echo "La release ${env.BRANCH_NAME} a été déployé sur l'environnement ${params.ENV}"
}