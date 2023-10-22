# DevOps TP2 – Jenkins CI
## Objectives:
- Create a FreeStyle Project: Configure and run a Jenkins FreeStyle project using source code management, build steps, and progress messages.
- Configure a Pipeline Project: Create a Jenkins Pipeline project using a Jenkinsfile, with build steps, step messages, and integrate a trigger to check SCM modifications.
- Understand Continuous Integration: Gain a basic understanding of the continuous integration concept and how Jenkins facilitates the automation of software development tasks.
  
## Part 1: FreeStyle Project
### Step 1: Initial Jenkins Configuration
1. Ensure Jenkins is installed and running on your server.
2. Open a web browser and access the Jenkins interface using the URL `http://localhost:8080.`

![Capture 2](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/57811743-4255-4782-877c-dd2d605782a4)

### Step 2: Creating a FreeStyle Project
1. On the Jenkins dashboard, click on "New Item."
2. In the opened window:
   - Name your FreeStyle project, e.g., "MyFreeStyleProject."
   - Choose "Freestyle project."
   - Click "OK" to create the project.


![Capture 3](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/a55302c3-373d-4f2a-8823-83178fb11816)

### Step 3: FreeStyle Project Configuration
1. In the FreeStyle project configuration page, under "Source Code Management," ensure you have correctly configured your SCM (e.g., Git).
I chose last year's Mini Microservices project

![Capture 4](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/d103daaf-feb1-4a17-beb0-a1d63838b297)


2. Under "Build Triggers," check the "Poll SCM" option.
3. In the "Build Schedule" field, enter the following cron expression to trigger SCM check every 5 minutes: `*/5 * * * *`

![Capture 5](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/d820b69b-c233-40d9-9169-e81a3c7e0dba)

4. Under "Build," add steps using shell commands with echo to display messages at each step.

![Capture 6](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/661606ae-0751-486d-9dcb-a9d6647ab421)

### Step 4: Running the FreeStyle Project
1. Click "Save" to save the FreeStyle project configuration.
2. Click "Build Now" to run the FreeStyle project.

![Capture 8](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/61677043-dd07-4d95-a261-7de26bfdbcb4)

3. Track the build progress by clicking on the project and checking the build logs for messages at each step.

![Capture 9](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/c41beac7-d9b4-412e-8bda-9695571f91b2)

And this is MyFirstFreeStyle project

![Capture 10](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/047e3388-697e-4dd8-b170-f80cd1f576df)

## Part 2: Pipeline Project
### Step 1: Creating a Pipeline Project
1. Go back to the Jenkins dashboard.
2. Click on "New Item."
3. In the opened window:
    - Name your Pipeline project, e.g., "MyPipeline."
    - Choose "Pipeline" as the project type.
    - Click "OK" to create the Pipeline project.

![Capture 11](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/a702565f-120b-4c7a-ae52-05d9785a8d84)

### Step 2: Pipeline Project Configuration
1. In the Pipeline project configuration page, no need to configure a "Poll SCM" trigger as pipelines usually don't work that way. Instead, integrate SCM checking into your Jenkinsfile.
2. In the Jenkinsfile, use the pollSCM function to trigger SCM check every 5 minutes and use echo to display messages at each step.
```groovy
pipeline {
    agent any
    triggers {
        pollSCM('*/5 * * * *')
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Récupération du code source"
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Installation des dépendances"
                echo "Build du projet"
                echo "Exécution des tests"
            }
        }
        stage('Deploy') {
            steps {
                echo "Déploiement du projet"
      
            }
        }
    }
}
```
Or you can use the Pipeline script as shown below: 

![Capture 12](https://github.com/hadil-kortas/TP2-Jenkins/assets/97675597/65813df8-6421-4ff0-97e9-8b622e822b44)












