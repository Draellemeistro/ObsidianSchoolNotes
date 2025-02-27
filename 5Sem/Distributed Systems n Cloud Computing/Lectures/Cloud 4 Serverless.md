# bla bla
## AWS serverless course
- Microservices & [[Serverless Computing]]
- [[Event-Driven Architecture]]
- AWS Lambda: Configure and Monitor
	- best practices
- Features & benefits of additional serverless features
## Notes
- **Containers take time to spin up!**
	- Cold start proble

# Overview
## **[[Terms_L4-Serverless_Computing|Overview L4]]** ----- [[Cloud 4 Serverless]]
## All L4 Terms
- AWS Lambda
- [[Serverless Computing]] Concepts
- [[Event-Driven Architecture]]
- [[AWS Lambda]]
- Stateless Functions
- Function Triggers
- Monitoring Lambda Functions
## Tools
- Google Cloud Functions
- Document AI Pipeline
## Questions and Thoughts
- What are the key differences between serverless and traditional compute models?
- How can serverless architectures reduce operational overhead?
## Relevant Terms from Other Lectures
- Orchestration (L5: **[[Terms_L5-Kubernetes|Overview L5]]** ----- [[Cloud 5 Kubernetes]])
- Kubernetes (L5: **[[Terms_L5-Kubernetes|Overview L5]]** ----- [[Cloud 5 Kubernetes]])

# Exercises
## Build an End-to-End Data Capture Pipeline using Document AI (uses cloud functions, the Google Cloud's equivalent of AWS lambda): [HER](https://www.cloudskillsboost.google/focuses/21027?locale=en&parent=catalog)

![[Pasted image 20241001100920.png]]
1. Upload forms with address data to Cloud Storage.
2. The upload triggers a Cloud Function call to process the forms.
3. Document AI called from Cloud Function.
4. Document AI JSON data saved back to Cloud Storage.
5. Form Data written to BigQuery by Cloud Function.
6. Cloud Function sends addresses to a Pub/Sub topic.
7. Pub/Sub message triggers Cloud Function for GeoCode processing.
8. Geocoding API called from Cloud Function.
9. Geocoding data written to BigQuery by Cloud Function.


