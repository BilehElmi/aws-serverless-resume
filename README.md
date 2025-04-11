# AWS Serverless Resume Website

This project demonstrates how to build and host a **serverless resume website** using AWS services such as **S3**, **Lambda**, **API Gateway**, and **DynamoDB**. The website displays a dynamic visitor counter powered by AWS cloud-native solutions.

## **Features**
- Static resume website hosted on Amazon S3.
- Visitor counter implemented using:
  - **DynamoDB**: To store the visitor count.
  - **AWS Lambda**: To handle backend logic for incrementing and retrieving the count.
  - **API Gateway**: To expose the Lambda function via a RESTful API.
- Fully serverless architecture with no need for traditional servers.
- Responsive design using HTML, CSS, and JavaScript.

---

## **How It Works**
1. **Frontend**:
   - The resume is written in HTML and styled with CSS.
   - JavaScript fetches the visitor count from the API Gateway endpoint and dynamically displays it on the website.

2. **Backend**:
   - A DynamoDB table stores the visitor count with a simple schema (`id` and `visitCount`).
   - A Lambda function updates the visitor count in DynamoDB and returns the updated value.
   - API Gateway exposes the Lambda function to handle HTTP GET requests.

3. **Hosting**:
   - The static files (`index.html`, `styles.css`, etc.) are hosted on an Amazon S3 bucket configured for static website hosting.

---

## **Architecture Diagram**
+-----------------------+ +-----------------------+
| Browser (Client) | | AWS API Gateway |
| | | |
| HTML + CSS + JS | <----> | Routes HTTP Requests |
+-----------------------+ +-----------------------+
| |
v v
+-----------------------+ +-----------------------+
| Amazon S3 Bucket | | AWS Lambda |
| (Static Website Files)| | Updates Visitor Count |
+-----------------------+ +-----------------------+
|
v
+-----------------------+
| Amazon DynamoDB |
| Stores Visitor Count |
+-----------------------+

---

## **Getting Started**

### Prerequisites
To replicate this project, you’ll need:
- An AWS account.
- Basic knowledge of AWS services like S3, Lambda, DynamoDB, and API Gateway.
- Familiarity with HTML, CSS, and JavaScript.

---

### Steps to Build This Project

#### 1. Create a Static Website on S3
- Create an S3 bucket and enable static website hosting.
- Upload your `index.html` and `styles.css` files to the bucket.
- Configure public access permissions for your bucket.

#### 2. Set Up DynamoDB
- Create a DynamoDB table named `VisitorCounter` with:
  - Partition Key: `id` (String).
  - Add an initial item: `{ "id": "visitor", "visitCount": 0 }`.

#### 3. Write the Lambda Function
- Create a Lambda function in Python or Node.js to:
  - Increment the visitor count in DynamoDB.
  - Return the updated count as a JSON response.

#### 4. Configure API Gateway
- Create an HTTP API in API Gateway.
- Link it to your Lambda function with a `/visitor` route.
- Enable CORS to allow requests from your S3-hosted website.

#### 5. Integrate Frontend with Backend
- Add JavaScript to fetch the visitor count from the API Gateway endpoint.
- Display the count dynamically on your webpage.

#### 6. Test Everything
- Test your website by visiting its URL and verify that:
  - The visitor counter increments correctly.
  - The page loads without errors.

---

## **How to Use This Repository**
This repository contains:
1. `index.html`: The main HTML file for your resume website.
2. `styles.css`: Stylesheet for styling the webpage.
3. `README.md`: Documentation for this project.

### Instructions
1. Clone this repository:
2. git clone https://github.com/yourusername/aws-serverless-resume.git

2. Follow the steps in [Getting Started](#getting-started) to set up your own serverless resume website.

---

## **Live Demo**
Check out my live resume website: [Your Resume URL](https://bileh-resume.s3.us-west-2.amazonaws.com/Resume+Web+Project/index.html)

---

## **Lessons Learned**
This project helped me:
1. Understand how to use AWS services together to build serverless applications.
2. Troubleshoot common issues like CORS errors and data serialization problems in Lambda functions.
3. Deploy a fully functional static website integrated with backend logic.

---

## **Contributing**
Feel free to fork this repository and submit pull requests if you'd like to improve or extend this project!

---

## **License**
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

## **Acknowledgments**
Special thanks to:
- [AWS Documentation](https://aws.amazon.com/documentation/) for detailed guides on using their services.
- The #CloudResumeChallenge community for inspiration.

