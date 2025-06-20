# Content 
# Assessment Task: Data Source API Analyst

This repository contains the solution for the assessment task for the Data Source API Analyst role. The project's goal is to demonstrate the ability to research, test, and extract data from the GitHub REST API, as well as to document the process in a clear and structured manner.

## Repository Structure

The project is organized as follows:

-   **/Content**: Contains the generated artifacts, including the Google Colab notebook (`.ipynb`) with the Python code for data extraction and the approach documentation.
-   **/Postman_Collection**: A folder intended for the Postman collection. Although the main approach was via Google Colab, this folder was kept to follow the requested structure.
-   **README.md**: This file, which serves as the project's central documentation.

## Methodology and Approach

The task was executed following the proposed steps, with a focus on automation and good programming practices.

### 1. API Research (Step 1)

The first step consisted of researching the official GitHub REST API documentation to identify the necessary endpoints to meet the following requirements:

1.  **Search Public Repositories**: `GET /search/repositories`
2.  **Get Commit Data**: `GET /repos/{owner}/{repo}/commits`
3.  **Extract Repository Content**: `GET /repos/{owner}/{repo}/contents/{path}`

### 2. Data Extraction with Google Colab (Step 3)

**Google Colab** was chosen for data extraction to earn the bonus points and to create a more robust and automated solution in Python. The notebook `Data_Source_API_Analyst_Homework.ipynb`, located in the `/Content` folder, implements the following features:

-   **Secure Authentication**: The script requires a GitHub Personal Access Token (PAT) to authenticate requests, ensuring access to higher rate limits.
-   **Modular Requests**: Separate functions were created for each of the three requirements, making the code clean and reusable.
-   **Pagination Handling**: The code automatically handles paginated API responses, using loops to iterate through all pages of results and consolidate the data.
-   **Error Handling**: The script uses `try-except` blocks to catch and handle potential API errors, such as malformed requests or permission issues.

### 3. Troubleshooting Guide (Step 4)

The approach to handling common issues is implemented directly within the Python script:

-   **`401 Unauthorized` Error**: The script checks the response of the first authenticated request. If a 401 error occurs, it informs the user that the provided token is invalid or has expired.
-   **Rate Limiting**: The script catches the `403 Forbidden` error. Upon encountering this, it inspects the API response headers (`X-RateLimit-Remaining` and `X-RateLimit-Reset`) and informs the user when the rate limit will be reset, pausing execution if necessary.

## Personal Reflection (Step 5)

*[Here you will add your personal reflection on the task. Describe the challenges you encountered (e.g., understanding the API response structure, handling pagination), what you learned during the process, and how this task connects with your skills as a data analyst.]*
