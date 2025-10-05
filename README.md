# devops_101

## Jenkins CI/CD Setup

This repository is configured to work with Jenkins for continuous integration and continuous deployment.

### Prerequisites

- Jenkins server installed and running
- Required Jenkins plugins:
  - Pipeline plugin
  - Git plugin
  - Credentials Binding plugin

### Setting Up Jenkins Pipeline

1. **Create a New Pipeline Job:**
   - Log in to your Jenkins dashboard
   - Click "New Item"
   - Enter a name for your job (e.g., "devops_101")
   - Select "Pipeline" and click "OK"

2. **Configure the Pipeline:**
   - In the job configuration, scroll to the "Pipeline" section
   - Under "Definition", select "Pipeline script from SCM"
   - Select "Git" as the SCM
   - Enter your repository URL: `https://github.com/rayengeudri/devops_101.git`
   - Specify the branch (e.g., `*/main`)
   - Script Path: `Jenkinsfile`
   - Click "Save"

3. **Run the Pipeline:**
   - Click "Build Now" to trigger the pipeline
   - Monitor the build progress in the console output

### Pipeline Stages

The Jenkinsfile defines the following stages:

1. **Checkout**: Retrieves the code from the repository
2. **Build**: Compiles and builds the application
3. **Test**: Runs automated tests
4. **Code Quality**: Performs code quality checks
5. **Deploy**: Deploys the application

### Customizing the Pipeline

Edit the `Jenkinsfile` to customize the pipeline according to your project needs:

- Add specific build commands (npm, maven, gradle, etc.)
- Configure test frameworks
- Set up deployment targets
- Add environment-specific configurations

### Webhook Integration (Optional)

To trigger builds automatically on code push:

1. In GitHub, go to repository Settings > Webhooks
2. Click "Add webhook"
3. Payload URL: `http://your-jenkins-server/github-webhook/`
4. Content type: `application/json`
5. Select "Just the push event"
6. Click "Add webhook"

### Troubleshooting

- Ensure Jenkins has proper credentials to access the repository
- Check Jenkins logs for detailed error messages
- Verify all required plugins are installed and up to date

### Additional Resources

- [Jenkins Documentation](https://www.jenkins.io/doc/)
- [Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)
- [Best Practices](https://www.jenkins.io/doc/book/pipeline/pipeline-best-practices/)