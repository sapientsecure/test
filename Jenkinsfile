node {
	env.WORKSPACE = pwd()
	echo "${env.WORKSPACE}"

		// Get the maven tool.
		// ** NOTE: This 'M3' maven tool must be configured
		// **       in the global configuration.           
		
		def mvnHome = tool 'M3'

		// Mark the code build 'stage'....
		stage 'Build'
		sh "${mvnHome}/bin/mvn clean install -f ${env.WORKSPACE}/junitmavenexample/pom.xml'"
		
		stage 'Email'
			
		mail body: "project build status will come here" ,
            from: 'jenkins@noreply.com',
            replyTo: 'rajat.bansal@hcentive.com',
            subject: 'project build status',
            to: 'rajat.bansal@hcentive.com'
	    attachments: "${env.WORKSPACE}/hello"
}
