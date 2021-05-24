pipeline {
// Initially run on any agent
    agent {
        label 'codesigning'
    }
    options { timestamps () }
    environment {
        //Set some defaults
        def workspace = pwd()
        def propsFileName = "foo.properties"
    }

    stages {

        stage("Get Properties") {
            // Download file propsFileName
            fileDownloadOperation url: "https://raw.githubusercontent.com/matthewchivers/test-jenkins-properties-properties/main/${propsFileName}"
        }
        stage("Read properies") 
        {
            def props = readProperties  file: propsFileName
            // print properties to test
            for (def key in props.keySet())
            {
                println "key = ${key}, value = ${props[key]}"
            }
        }
    }
}
