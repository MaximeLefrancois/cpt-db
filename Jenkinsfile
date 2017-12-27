
properties([
   parameters([
      string(defaultValue: 'horsprod', description: 'Quel environnement de deploiement ("prod" ou "horsprod")?', name: 'ENV_BACK'),
	  string(defaultValue: '', description: 'Identifiant compte AD', name: 'LOGIN'),
	  password(defaultValue: '', description: 'Password compte AD', name: 'PWD')
   ])
])

node {

	stage("Récupération des sources") {
		checkout scm
	}

	stage("Deploiement de l'application Db") {
		sh "echo APPLICATION-DB"
	}
	
	if (params.ENV_DB == 'prod') {
		stage("Deploiement de l'application Back en prod") {
			sh "echo APPLICATION-BACK"
		}
	}
	
	echo "La release ${env.BRANCH_NAME} a été déployé sur l'environnement ${params.ENV_DB}"
}