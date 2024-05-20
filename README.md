# Monitoring and Visibility Task

## Overview
This task involves setting up a simple Node.js application, Dockerizing it, deploying it on a Kubernetes cluster on Google Cloud Platform (GCP), and ensuring visibility and monitoring.

## Steps

1. **Set Up a Simple Node.js App:**
   - Create a basic Node.js application.

2. **Navigate to Google Cloud Platform (GCP):**
   - Access the Google Cloud Platform console [here](https://console.cloud.google.com/).

3. **Create an Artifact Registry:**
   - Go to the Artifact Registry section in GCP and create a new repository.
     <img width="816" alt="Screenshot 2024-05-20 at 4 39 53 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/8c924482-770c-4976-b542-8e031e33226a">

4. **Dockerize the App:**
   - Dockerize your Node.js application using:
     ```
     docker build --platform=linux/amd64 -t task10.1p:latest .
     ```
     <img width="1248" alt="Screenshot 2024-05-21 at 4 22 38 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/af2477ac-9ab0-4fe5-9f77-1a27909192d2">

5. **Tag the Docker Image:**
   - Tag the Docker image:
     ```
     docker tag <source_image>:<tag> docker.pkg.dev/<project_id>/<repository_name>/<target_image>:<tag>
     ```
     <img width="1231" alt="Screenshot 2024-05-20 at 5 22 14 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/ba72bddb-ef78-4d39-94c6-b4d7bd5bab77">

6. **Push the Docker Image:**
   - Push the Docker image to the Artifact Registry:
     ```
     docker push docker.pkg.dev/<project_id>/<repository_name>/<image>:<tag>
     ```
     <img width="1172" alt="Screenshot 2024-05-20 at 6 04 16 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/3fda121f-9047-4aa3-a639-d66c623e1ede">


7. **Create a Kubernetes Cluster:**
   - Create a Kubernetes cluster in GCP.
     <img width="1391" alt="Screenshot 2024-05-21 at 5 12 56 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/a9e14953-0f42-417b-974b-6a51d4e4ebff">


8. **Connect to the Cluster:**
   - Access the Kubernetes cluster via the GCP console.
     <img width="1060" alt="Screenshot 2024-05-20 at 6 10 45 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/72a9d587-d420-40d6-b113-f8ae643cab5b">


9. **Open Google Cloud Shell Terminal:**
   - Open the Google Cloud Shell terminal from the GCP console.
    <img width="366" alt="Screenshot 2024-05-20 at 6 07 21 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/e03f0151-4160-46d6-9092-267bce05bdb9">


10. **Create a Deployment:**
    - Use the following command to create a Kubernetes deployment:
      ```
      kubectl create deployment <deployment_name> --image=<image_name>:<tag>
      ```
      <img width="1371" alt="Screenshot 2024-05-20 at 6 11 24 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/fb8971cd-8f83-4af2-98f0-4d8db5c5fd43">

      

11. **Check Pod Status:**
    - Verify pod status:
      ```
      kubectl get pods
      ```
      <img width="574" alt="Screenshot 2024-05-21 at 4 26 03 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/be88d485-b2a5-499a-a1b3-72050e33f177">


12. **Expose the Deployment:**
    - Expose the Kubernetes deployment as a service:
      ```
      kubectl expose deployment <deployment_name> --type <service_type> --port <port> --target-port <target_port>
      ```
      <img width="1346" alt="Screenshot 2024-05-20 at 6 13 08 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/ecf4529b-913f-4a78-b859-68ad046758ef">

      

13. **Check Service Status:**
    - Verify service status:
      ```
      kubectl get service <service_name>
      ```
      <img width="729" alt="Screenshot 2024-05-20 at 6 13 48 PM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/0c0fbaf1-9fc0-4eb3-9401-7bbc90e380ff">

14. **Testing:**
    - <img width="388" alt="Screenshot 2024-05-21 at 4 29 20 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/d1aa9393-dc46-4113-95e3-3e7e9004f1a6">

    - <img width="610" alt="Screenshot 2024-05-21 at 4 30 08 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/f23f43da-6f61-4ecc-adfb-ce65d1e95f19">

15. **Monitoring:**

    <img width="980" alt="Screenshot 2024-05-21 at 4 43 03 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/dd0a5140-3cff-4954-bb82-79bdee34bbb5">
    <img width="975" alt="Screenshot 2024-05-21 at 4 44 04 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/83a657a9-d96f-458f-8f50-ba28483fe2ae">
    <img width="980" alt="Screenshot 2024-05-21 at 4 43 55 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/e40138d0-d160-4674-9a34-96a102f5d42b">
    <img width="981" alt="Screenshot 2024-05-21 at 4 43 33 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/2cc3ec86-b8e3-4bd3-aa14-5607203aed91">
    <img width="979" alt="Screenshot 2024-05-21 at 4 43 24 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/6ce1a0fc-9dcb-49e6-844d-36a77a1e4f05">
    <img width="974" alt="Screenshot 2024-05-21 at 4 43 11 AM" src="https://github.com/gaurav3444/sit323-737-2024-t1-prac10P/assets/66586901/161589b8-bffb-45c2-a1f6-d431f216c442">


## Conclusion
These steps provide a comprehensive guide for setting up a Node.js application, Dockerizing it, deploying it on a Kubernetes cluster on GCP, and ensuring visibility and monitoring.



   

