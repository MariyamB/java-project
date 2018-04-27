stages {
    stage("Build") {
        steps {
            echo "Building application..."
            script
            {
            ant -f reports/result.xml.xml -v
            }
        }
    }
}
