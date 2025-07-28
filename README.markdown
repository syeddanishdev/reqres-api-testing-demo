# ReqRes API Testing Demo with Postman and CI/CD

This project demonstrates advanced API testing using Postman with the ReqRes public API (https://reqres.in/). It showcases skills in creating Postman collections, writing JavaScript for pre-request and test scripts, generating reports, and automating testing with a CI/CD pipeline using GitHub Actions. This project is ideal for showcasing on a resume and for learners exploring API testing.

## Project Overview

The collection includes tests for:
- Listing all users (GET)
- Retrieving a single user (GET)
- Creating a new user (POST)
- Updating a user (PATCH)

### Features
- **Collection Variables**: Manages base URL and dynamic data across requests.
- **Pre-request Scripts**: Generates dynamic data (e.g., random user names, timestamps).
- **Test Scripts**: Validates response status, response time, and data integrity.
- **Chaining Requests**: Reuses data (e.g., user ID) between requests.
- **Reporting**: Generates HTML reports using Newman.
- **CI/CD Pipeline**: Automates testing and report generation via GitHub Actions.

## Prerequisites
- [Postman](https://www.postman.com/downloads/)
- [Node.js](https://nodejs.org/) (for local Newman reports)
- Newman (`npm install -g newman newman-reporter-htmlextra`)
- [GitHub account](https://github.com/) (for CI/CD)

## Setup Instructions
1. **Import the Collection**:
   - Download `ReqRes_API_Testing_Demo.postman_collection.json` from this repository.
   - In Postman, go to `File > Import`, select the JSON file, and import it.
2. **Run the Collection Locally**:
   - Open the collection in Postman.
   - Click `Run Collection` to execute all requests.
   - Review test results in Postman.
3. **Generate a Report Locally**:
   - Install Newman: `npm install -g newman newman-reporter-htmlextra`
   - Run:
     ```bash
     newman run ReqRes_API_Testing_Demo.postman_collection.json -r htmlextra --reporter-htmlextra-export report.html
     ```
   - Open `report.html` in a browser.
4. **Set Up CI/CD**:
   - Push the repository to GitHub.
   - The `.github/workflows/ci.yml` automates testing on push/pull requests to the `main` branch.
   - View results and download `report.html` from GitHub Actions.

## CI/CD Workflow
The GitHub Actions workflow:
- Installs Node.js and Newman.
- Runs the Postman collection.
- Generates an HTML report.
- Uploads the report as an artifact.

To view results:
- Go to GitHub repository > `Actions` tab.
- Select the latest workflow run.
- Download the `newman-report` artifact.

## Skills Demonstrated
- **API Testing**: Comprehensive test cases for status, response time, and data validation.
- **JavaScript**: Pre-request and test scripts for dynamic data and assertions.
- **Postman**: Collection variables, request chaining, and automation.
- **Reporting**: Professional HTML reports with Newman.
- **CI/CD**: Automated testing with GitHub Actions and artifact publishing.
- **Documentation**: Clear instructions for setup and learning.

## Learning Resources
- [Postman Documentation](https://learning.postman.com/docs/getting-started/introduction/)
- [Newman](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/)
- [ReqRes API](https://reqres.in/)
- [Chai Assertions (used in Postman)](https://www.chaijs.com/)
- [GitHub Actions](https://docs.github.com/en/actions)

## Folder Structure
```
├── .github/workflows/ci.yml                         # GitHub Actions workflow
├── ReqRes_API_Testing_Demo.postman_collection.json  # Postman collection
├── README.md                                       # Documentation
└── report.html                                     # Generated report (after Newman)
```

## For Learners
- **Explore the Collection**: Open in Postman to see request structures and scripts.
- **Study JavaScript**: Review pre-request and test scripts for dynamic data handling.
- **Learn CI/CD**: Check the GitHub Actions workflow to understand automation.
- **Generate Reports**: Run Newman locally to see HTML report output.

This project is licensed under the MIT License.