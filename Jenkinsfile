parallel {
	'Build Frontend': {
		stage('Build') {
			when {
				anyOf {
					branch 'master'
					branch 'frontend'
				}
			}
			agent {
				dockerfile {
					filename 'Dockerfile'
					dir 'frontend'
					args '-u root -p 49600:80'
				}
			}
			steps {
				sh './bin/frontened-build.sh'
				input message: 'Finished using the web site? (Click "Proceed" to continue)'
			}
		}
	}
	'Build Backend': {
		stage('Build') {
			when {
				anyOf {
					branch 'master'
					branch 'backend'
				}
			}
			agent {
				dockerfile {
					filename 'Dockerfile'
					dir 'frontend'
					args '-u root -p 49600:80'
				}
			}
			steps {
				sh './bin/frontened-build.sh'
				input message: 'Finished using the web site? (Click "Proceed" to continue)'
			}
		}
	}
}
