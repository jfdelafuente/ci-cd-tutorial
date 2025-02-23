# Tutorial para CI/CD con Docker, GitHub Action y GCP

Basado en el siguiente artículo [The CI/CD Handbook: Learn Continuous Integration and Delivery with GitHub Actions, Docker, and Google Cloud Run](
https://www.freecodecamp.org/news/learn-continuous-integration-delivery-and-deployment/)

## Objetives

- Set up a Node.js project. ✨
- Implement automated tests using Jest and Supertest. 🛠️
- Set up a CI/CD workflow using GitHub Actions, triggered on push, and pull requests, or after a new release. ⚙️
- Build and publish a Docker image of your application to Docker Hub. 📦
- Deploy your application to a staging environment for testing. 🚀
- Finally, roll it out to a production environment, making it live! 🌐


### Differences Between Continuous Integration, Continuous Delivery, and Continuous Deployment 🔍


| Aspect  | Continuous Integration (CI)  | Continuous Delivery (CD) | Continuous Deployment (CD) |
|---|---|---|---|
| Primary Focus  | Merging feature branches into the main/general codebase OR to the staging codebase.| Deploying the tested code to a staging environment for QA testing and approval. | Automatically deploying the code to the live production environment. |
| Automation Level | Automates testing and building processes for feature branches.	|Automates deployment to staging/test environments after successful testing. | Fully automates the deployment to production with no manual approval. |
| Testing Scope	| Automated tests run on feature branches to ensure code quality before merging into the main or staging branch. | Includes automated tests before deployment to staging and allows QA testers to perform manual testing in a controlled environment. | May include automated tests as a final check, ensuring the production environment is stable before deployment. |
| Branch Involved | Feature branches merging into the main/general or staging branch. | Staging branch used as an intermediate step before merging into the main branch. | Main/general branch deployed directly to production. |
| Environment Target | Ensures integration and testing within a local environment or build pipeline. | Deploys to staging/test environments where QA testers validate features.	| Deploys to production/live environment accessed by end users.|
| Key Goal | Prevent integration conflicts and ensure new changes don’t break the existing codebase. | Provide a stable, near-production environment for thorough QA testing before final deployment. | Ensure that new features and updates reach users as soon as possible with minimal delays. |
| Approval Process | No approval needed. Feature branches are tested and merged upon passing criteria. | QA team or lead provides feedback/approval before changes are merged into the main branch for production. | No manual approval. Deployment is entirely automated. |
| Example Trigger | A developer merges a feature branch into the main branch. | The staging branch passes automated tests (during PR) and is ready for deployment to the testing environment. | A new release is created or a pull request is merged into the main branch, triggering an automatic production deployment. |
