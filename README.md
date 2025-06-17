QA Automation CI/CD Workflow Documentation
Overview
This document outlines the standard QA automation workflow across multiple environments using Katalon Studio and Git. The roles and responsibilities are distributed across Intern QA (DEV), Jr. QA (SIT), and Sr. QA (UAT) to ensure quality and continuity in CI/CD processes.
Tools Used
•	Katalon Studio – For automation scripting and execution
•	Git – For version control and collaboration
•	CI/CD Pipeline (Optional) – For test automation execution across environments
Environment Roles
Environment	Role	Responsibility
DEV	Intern QA	Create and push feature-based automated test cases
SIT	Jr. QA	Review, refine, and validate intern scripts
UAT	Sr. QA	Final approval, integration, and CI/CD management
Intern QA – DEV Environment
Purpose
Develop initial test cases using Record & Run in Katalon. Work locally and push only the assigned feature test files.
Workflow
1.	Open Katalon Studio
•	Use a clean local Katalon project.
2.	Create Test Cases via Record & Run
•	Save tests under /Test Cases/FeatureName/
•	Object Repository will be auto-generated: /Object Repository/FeatureName/
•	Group in a Test Suite: /Test Suites/Intern/FeatureName/
3.	Test Locally
•	Run and validate locally before pushing.
4.	Push Only Specific Folders to Git
•	git init
•	git add "Test Cases/YourFeature"
•	git add "Object Repository/YourFeature"
•	git add "Test Suites/Intern/YourFeature"
•	git commit -m "Added [Feature] test automation by [Intern Name]"
•	git push origin dev

Folder Naming Guidelines
•	Feature Folder Naming: Use clear, lowercase names, e.g., login, registration, checkout
•	Test Case Naming: [Platform]_[Function/Module]_[Action or Condition], e.g., Web_Login_ValidCredentials

Jr. QA – SIT Environment
Purpose
Review, execute, and refactor intern test cases for the SIT environment.
Workflow
1.	Pull from dev Branch
•	Review newly added folders and files.
2.	Run in Katalon Studio
•	Validate functionality in SIT configuration.
3.	Refactor Tests
•	Improve object naming
•	Remove redundant steps
•	Add validations
4.	Move Tests to SIT Folder
•	/Test Cases/SIT/FeatureName/
•	/Object Repository/SIT/FeatureName/
•	/Test Suites/SIT/FeatureName/
5.	Push to sit Branch
•	git checkout -b sit
•	git add "Test Cases/SIT/FeatureName"
•	git add "Object Repository/SIT/FeatureName"
•	git add "Test Suites/SIT/FeatureName"
•	git commit -m "Refined [Feature] test scripts"
•	git push origin sit

Sr. QA – UAT Environment
Purpose
Conduct final validation, prepare for release, and manage CI/CD integration.
Workflow
1.	Pull from sit Branch
•	Import reviewed test cases
2.	Run & Validate in UAT
•	Configure data and environment-specific settings
3.	Finalize Tests in UAT Folder
•	/Test Cases/UAT/FeatureName/
•	/Object Repository/UAT/FeatureName/
•	/Test Suites/UAT/FeatureName/
4.	Push to uat Branch
•	git checkout -b uat
•	git add "Test Cases/UAT/FeatureName"
•	git add "Object Repository/UAT/FeatureName"
•	git add "Test Suites/UAT/FeatureName"
•	git commit -m "Finalized [Feature] for UAT"
•	git push origin uat

5.	CI/CD Integration (Optional)
•	Trigger automated test runs in Jenkins/GitHub Actions
•	Monitor UAT execution reports
Summary
This documentation ensures structured contributions from Interns to Sr. QA while minimizing conflicts and enforcing quality. Each level reviews and builds upon the previous, aligning with CI/CD best practices.

![Uploading image.png…]()
