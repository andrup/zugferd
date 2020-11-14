pipeline {
  agent any
  stages {
    stage('Download Requirements') {
      steps {
        sh 'wget https://getcomposer.org/download/1.10.13/composer.phar -O composer.phar'
        sh 'wget http://phpdox.de/releases/phpdox.phar -O phpdox.phar'
        sh 'wget https://phpdoc.org/phpDocumentor.phar -O phpDocumentor.phar'
        sh 'chmod +x ./composer.phar'
        sh 'chmod +x ./phpdox.phar'
        sh 'chmod +x ./phpDocumentor.phar'
      }
    }

    stage('Prepare') {
      steps {
        sh 'mkdir ./build/builddoc'
        sh 'mkdir ./build/doc'
        sh 'mkdir ./build/coverage'
        sh 'mkdir ./build/logs'
        sh 'mkdir ./build/pdepend'
        sh 'mkdir ./build/phpdox'
        sh 'mkdir ./build/dist'
      }
    }

    stage('Install') {
      steps {
        sh 'php ./composer.phar install --prefer-dist --no-progress'
        sh 'php ./composer.phar update --dev'
      }
    }

  }
}