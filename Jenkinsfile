pipeline {
	agent any
		stages{
			stage('One') {
				steps {
					echo 'Hi, this is ankita'
				}	
			}
                        stage('Two') {
				steps {
					input('Do you want to proceed?')
				}
			}
			stage('Three') {
				when {
					not {
						branch 'master'
					}
				}
				steps {
					echo "Hello"
				}
			}
			stage('Four')  {
					parallel {
						stage ('Unit Test') {
									steps {
										echo "Running the unit Test....."
									}
						}
						stage ('Integration test') {
									agent {
										docker {
											reuseNode fals
											image 'ubuntu'
										}
									}
									steps {
										echo "Running the integration Test.."
									}
						}
					}
			}
			}
			}
			}
					
