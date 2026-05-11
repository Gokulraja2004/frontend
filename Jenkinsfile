pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Gokulraja2004/frontend.git'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                sudo systemctl start apache2

                sudo rm -rf /var/www/html/*

                sudo cp -r . /var/www/html/

                sudo chmod -R 755 /var/www/html

                sudo systemctl restart apache2
                '''
            }
        }

    }
}