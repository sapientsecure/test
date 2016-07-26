node {
	env.WORKSPACE = pwd()
	echo "${env.WORKSPACE}"
		// Mark the code checkout 'stage'....
		stage 'Checkut'
			checkout scm
		//  svn 'https://svn.hcinternal.net/svn/PLATFORM/MAHIX/MAHIX/trunk'
		// Get some code from a GitHub repository
//		  git url: 'https://github.com/sapientsecure/test.git' ,branch: 'master'
		//svn url: 'https://svn.hcinternal.net/svn/PLATFORM/MAHIX/MAHIX'

		// Get the maven tool.
		// ** NOTE: This 'M3' maven tool must be configured
		// **       in the global configuration.           
		def mvnHome = tool 'M3'

		// Mark the code build 'stage'....
		stage 'Build'
		// Run the maven build
		//sh "${mvnHome}/bin/mvn clean install -f ${env.WORKSPACE}/'Java Project/pom.xml'"
		sh "echo hello"
		stage 'Email'
emailext attachLog: true, attachmentsPattern: 'Java Project/target/surefire-reports/*', body: 'Build BOdy comes here ', compressLog: true, subject: 'Build job ', to: 'rajat.bansal@hcentive.com'
     
}
