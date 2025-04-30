pipeline {
    agent any // Ejecuta el pipeline en cualquier agente disponible

    tools {
        // Define las herramientas necesarias que Jenkins debe tener instaladas
        maven 'Maven_3.8.6' // Nombre del Maven configurado en Jenkins
        jdk 'Java_17'       // Nombre del JDK configurado en Jenkins
    }

    stages {
        stage('Clonar Repositorio') {
            steps {
                // Esta etapa se puede personalizar para hacer git clone, pero aquí es solo ilustrativa
                echo 'Clonando repositorio...' 
            }
        }

        stage('Compilar Proyecto') {
            steps {
                // Limpia el proyecto y compila el código fuente
                sh 'mvn clean compile'
            }
        }

        stage('Ejecutar Pruebas') {
            steps {
                // Ejecuta las pruebas unitarias del proyecto
                sh 'mvn test'
            }
        }

        stage('Construir Artefacto') {
            steps {
                // Construye el archivo JAR del proyecto
                sh 'mvn package'
            }
        }

        stage('Finalizar') {
            steps {
                // Mensaje de cierre del pipeline
                echo '¡Pipeline completado correctamente!'
            }
        }
    }

    post {
        // Bloque de acciones que se ejecutan después del pipeline, según el resultado
        success {
            echo '✅ Éxito: todo funcionó.' // Si todo salió bien
        }
        failure {
            echo '❌ Fallo: algo salió mal.' // Si alguna etapa falló
        }
    }
}
