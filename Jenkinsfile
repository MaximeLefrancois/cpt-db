
properties([
   parameters([
      string(defaultValue: 'horsprod', description: 'Quel environnement de deploiement ("prod" ou "horsprod")?', name: 'ENV_DB'),
	  booleanParam(defaultValue: false, description: 'Déploiement auto', name: 'AUTO_PARAM'),
	  string(defaultValue: '', description: 'Identifiant compte AD', name: 'LOGIN'),
	  password(defaultValue: '', description: 'Password compte AD', name: 'PWD')
   ])
])

echo "La valeur de AUTO_PARAM est de :${AUTO_PARAM}."

def Boolean auto = AUTO_PARAM

echo "La valeur de auto est de :${auto}."

node {

	if (LOGIN != '' && PWD != '') {
		sh "echo le login est :${LOGIN} et le mot de passe est ${PWD}. "
	} else {
		sh "echo Pas de login ni de password"
	}
		
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
	
	if (AUTO_PARAM == 'true') {
		echo 'Déploiement automatique'
	}
	
	echo "La release ${env.BRANCH_NAME} a été déployé sur l'environnement ${params.ENV_DB}"
}