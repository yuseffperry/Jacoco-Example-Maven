{\rtf1\ansi\deff0\nouicompat{\fonttbl{\f0\fnil\fcharset0 Calibri;}}
{\*\generator Riched20 10.0.16299}\viewkind4\uc1 
\pard\sa200\sl276\slmult1\f0\fs22\lang9 pipeline \{\par
    agent any\par
\par
    stages \{\par
        stage('SCM Checkout') \{\par
            steps \{\par
                checkout([$class: 'GitSCM', \par
                    branches: [[name: '*/master']], \par
                    doGenerateSubmoduleConfigurations: false, \par
                    extensions: [], \par
                    submoduleCfg: [], \par
                    userRemoteConfigs: [[credentialsId: '1228b7b9-7260-4dfb-95b1-b0e8df31adf0', \par
                    url: 'git@github.com:yuseffperry/Jacoco-Example.git']]])\par
            \}\par
        \}\par
        stage('Build') \{\par
            steps \{\par
                sh './jenkins_build.sh'\par
                junit '*/build/test-results/*.xml'\par
                step( [ $class: 'JacocoPublisher' ] )\par
            \}\par
        \}\par
        stage('Test') \{\par
            steps \{\par
                echo 'Testing..'\par
            \}\par
        \}\par
        stage('Deploy') \{\par
            steps \{\par
                echo 'Deploying....'\par
            \}\par
        \}\par
    \}\par
\}\par
}
 