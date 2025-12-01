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

## Project Structure
├── collections/<br>
│ └── JSONPlaceholder API Tests.postman_collection.json<br>
├── .github/<br>
│ └── workflows/<br>
│ └── postman-newman-ci.yml<br>
└── README.md<br>

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
• Summary dashboard<br>
• Detailed request/response logs<br>
• Passed/failed tests<br>
• Execution time per request<br>
• Error traces (if any)<br>
