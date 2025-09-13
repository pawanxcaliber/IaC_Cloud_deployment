### Static Site with CI/CD on Render

This project demonstrates a complete DevOps and DevSecOps workflow for deploying a simple static website. The entire process—from code commit to live deployment—is automated using a CI/CD pipeline, ensuring that every change is validated and deployed securely.

### Key Technologies

*   **Render**: Cloud platform for hosting the static website.
    
*   **GitHub**: Used for version control and hosting the CI/CD pipeline.
    
*   **GitHub Actions**: The automation engine for the CI/CD pipeline.
    
*   **render.yaml**: The Infrastructure as Code (IaC) file that defines the service on Render.
    
*   **html-validate**: A static analysis tool for checking HTML code.
    

### CI/CD & DevSecOps

The CI/CD pipeline, defined in ci.yaml, is the core of this project. It ensures that every code change is validated and deployed automatically.

*   **Continuous Integration (CI)**: When code is pushed, the pipeline runs a **static code analysis (SAST)** step using html-validate to lint the HTML and check for security vulnerabilities or syntax errors before any deployment can occur.
    
*   **Continuous Deployment (CD)**: Upon a successful CI run, the pipeline triggers a new deployment to Render using a secure API call.
    

**DevSecOps Practices Applied:**

*   **Infrastructure as Code (IaC)**: The render.yaml file serves as a **blueprint**, defining the entire service configuration on Render. This makes the infrastructure version-controlled, auditable, and reproducible.
    
*   **Secrets Management**: Sensitive credentials, such as the RENDER\_API\_KEY, are stored as **GitHub Secrets**. The pipeline accesses them at runtime, preventing them from being exposed in the code or logs.
    
*   **Automation**: The pipeline automates the entire process, reducing manual errors and ensuring that security checks are consistently applied to every commit.
    

### Deployment

This project is deployed to Render using a Blueprint. Once the repository is connected to Render, the platform automatically detects the render.yaml file and uses it to provision and deploy the static site. After the initial setup, every push to the main branch automatically triggers a new deployment.
