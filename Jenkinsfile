stages {
    stage("Build") {
        steps {
            echo "Building application..."
            script
            {
            ant -f test.xml -v
            buildFile('reports/result.xml')
            }
        }
    }
}
