# Base framework features

- Execution Command
- package.json
- Mochawesome Report
- Video fetaures
- Screenshot feature

# Execution Command
<!-- Run all spec files under path >> "cypress > e2e"  -->
npm test

# package.json

Following scripts are defined - 
<!-- Pretest - clean report folder structure before every run -->
    "pretest": "rm -rf cypress/report"

<!-- Posttest - execution json file generation & html report generation   -->
    "posttest": "npm run mochawesome_filemerge && npm run mochawesome_reportgen"

<!-- Test - run the test, create necessary folder in the report directory -->
    "test": "npm run mochawesome_run && mkdir cypress/report/mochawesome-merge cypress/report/mochawesome-report",

<!-- Mochawesome Commands -->
    "mochawesome_run" : "npx cypress run -r mochawesome",
    "mochawesome_filemerge" : " npx mochawesome-merge cypress/report/mochawesome-json/*.json > cypress/report/mochawesome-merge/execution_report.json",
    "mochawesome_reportgen": "npx marge cypress/report/mochawesome-merge/execution_report.json --reportDir cypress/report/mochawesome-report"

# Mochawesome Report

- path >> "cypress > report"

## json file generation
- path "cypress > report > mochaweome-json"

The folder contains 'mochawesome.json' file/files generation for each spec file execution.

- path "cypress > report > mochaweome-merge"

The folder contains single 'execution_report' merge json file for html report generation.

- path "cypress > report > mochaweome-report"

The folder contains 'execution_report.html' report file with assets.

# Video and Screenshot WIP