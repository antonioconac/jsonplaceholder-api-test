# JSONPlaceHolder API Test Suite (Postman + Newman + GitHub Actions)
• This repository contains an automated API testing suite built with **Postman**, executed via **Newman**, and continuously validated using **GitHub Actions**.
<br><br>• The goal of this project is to demonstrate clean API testing practices, CI execution, and automated reporting for the public **jsonplaceholder.typicode.com** API.

## Features
✔ Full CRUD test coverage for **/posts** and **/todos**<br>
✔ Positive and negative test scenarios<br>
✔ Collection-level and folder-level assertions<br>
✔ Automated test execution using **Newman**<br>
✔ GitHub Actions CI pipeline<br>
✔ HTML reports generated after every run (I attached a HTML report as example)<br>
✔ Manual "Run Workflow" button in GitHub

## Defect reports
**While working on this project, based on how tests were written against a real-world API behavior, I found the following defects and I created defect reports for each one of them, using the structure learned while preparing for the ISTQB CTFL Exam:**

## Project Structure
├── collections/<br>
│ └── JSONPlaceholder API Tests.postman_collection.json<br>
├── .github/<br>
│ └── workflows/<br>
│ └── postman-newman-ci.yml<br>
└── README.md<br>

## Collection Structure

## Running Tests Locally
- Make sure you have **Node.js** installed, then install **Newman**:
- (bash) **npm install -g newman newman-reporter-htmlextra**

## Running the test collection
- (bash) **newman run "collections/JSONPlaceholder API Tests.postman_collection.json"**

## GitHub Actions CI
This repository includes a workflow file **(.github/workflows/postman-newman-ci.yml)**. The CI pipeline:<br>
- Installs Node + Newman<br>
- Runs the entire Postman collection<br>
- Generates HTML reports<br>
- Uploads them as artifacts<br>
<img width="916" height="377" alt="Screenshot 2025-12-01 122258" src="https://github.com/user-attachments/assets/1c6676f3-96e5-4ea4-b586-8f511fb01a09" />

### ✔ Triggering the Workflow Manually
You can run the tests anytime:<br>
1. Go to **Actions**<br>
2. Select **Postman Newman CI**<br>
3. Click **Run workflow**<br>

### ✔ Trigger on Push/Pull Requests
This workflow also runs automatically on:<br>
- any push to **main**<br>
- any pull request targeting **main**<br>

## 📊 Viewing the HTML Report
After each workflow run:<br>
1. Go to the **Actions** tab
2. Open the test run<br>
3. Scroll the **Artifacts** section<br>
4. Download **newman-report.zip**<br>
5. Extract and open **newman-report.html** in browser<br>

#### This file contains:
- Summary dashboard<br>
- Detailed request/response logs<br>
- Passed/failed tests<br>
- Execution time per request<br>
- Error traces (if any)<br>

## Technology Stack
- **Postman** - Test Design & scripting<br>
- **Newman** - CLI runner for Postman<br>
- **Node.JS** - Environment for Newman<br>
- **GitHub Actions** - CI automation<br>
- **HTMLEXTRA reporter** - Pretty HTML test reports<br>
<img width="1837" height="1038" alt="Screenshot 2025-12-01 122652" src="https://github.com/user-attachments/assets/76340af7-1596-463a-8613-a6bd8dc5bd8f" />

## What I learned?
- How to use Postman **Collection variables and environments** effectively<br>
<img width="1346" height="419" alt="Screenshot 2025-12-01 124251" src="https://github.com/user-attachments/assets/d51e8487-630a-4e9a-abb6-1c37f3313c20" />

- How to structure API tests into **positive/negative flows** (positive/negative, CRUD groups)<br><br>
<img width="370" height="765" alt="Screenshot 2025-12-01 123624" src="https://github.com/user-attachments/assets/57edfd7d-0099-47fe-a05a-b8ce629f9af5" /><br><br>

- How to remove redundancy using **collection- and folder- level tests**
- How to write maintainable tests scripts using **pm.expect**<br>

<img width="990" height="369" alt="Screenshot 2025-12-01 124353" src="https://github.com/user-attachments/assets/58b8e496-9b6d-4c35-a051-f09e2fc6275f" />
<img width="1017" height="591" alt="Screenshot 2025-12-01 124416" src="https://github.com/user-attachments/assets/a1207861-425f-46b0-b15f-74c8bec5f421" /><br>

- How to automate API tests using **Newman**<br>
<img width="846" height="466" alt="Screenshot 2025-12-01 125010" src="https://github.com/user-attachments/assets/92e4d94f-9cb1-4ae0-898c-1f296196c975" /><br>

- How to run tests in CI using **GitHub Actions**<br>
<img width="900" height="458" alt="Screenshot 2025-12-01 125229" src="https://github.com/user-attachments/assets/e14b5d27-90e4-4df5-9db9-d10ac0f2e2d7" /><br>

- How to generate & export **HTML reports** for debugging<br>
<img width="705" height="904" alt="Screenshot 2025-12-01 122107" src="https://github.com/user-attachments/assets/8c1ca07c-e1f0-413e-bd7f-d484e5b3cad9" /><br>
- How to organize a clean test project structure for long-term use<br>

## 📌 Future Improvements
- Add JSON schema validation<br>
- Add more edge-case tests (timeouts, performance checks, invalid types)<br>
- Export JUnit reports for test dashboards<br>
- Add Slack/Microsoft Teams notifications<br>
- Add scheduling (nightly runs)<br>
