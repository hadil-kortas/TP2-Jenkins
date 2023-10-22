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



