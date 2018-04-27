job('example') {
    steps {
        ant {
            ant -f test.xml -v
            buildFile('reports/result.xml')
            antInstallation('Ant 1.8')
        }
    }
}
