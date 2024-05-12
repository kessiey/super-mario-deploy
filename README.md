# SUPER-MARIO-DEPLOY

---

# How to Launch an Ubuntu Instance on AWS EC2

Follow these steps to launch an Ubuntu instance on AWS EC2:

## Step 1: Launch Ubuntu Instance

1. **Sign in to AWS Console**: Log in to your AWS Management Console.

2. **Navigate to EC2 Dashboard**: Go to the EC2 Dashboard by selecting “Services” in the top menu and then choosing “EC2” under the Compute section.

3. **Launch Instance**: Click on the “Launch Instance” button to start the instance creation process.

4. **Choose an Amazon Machine Image (AMI)**: Select an appropriate AMI for your instance. For example, you can choose the Ubuntu image.

5. **Choose an Instance Type**: In the “Choose Instance Type” step, select `t2.micro` as your instance type. Proceed by clicking “Next: Configure Instance Details.”

6. **Configure Instance Details**:
   - For “Number of Instances,” set it to 1 (unless you need multiple instances).
   - Configure additional settings like network, subnets, IAM role, etc., if necessary.
   - For “Storage,” click “Add New Volume” and set the size to 8GB (or modify the existing storage to 8GB).
   - Click “Next: Add Tags” when you’re done.

7. **Add Tags (Optional)**: Add any desired tags to your instance. This step is optional but helps in organizing instances.

8. **Configure Security Group**:
   - Choose an existing security group or create a new one.
   - Ensure the security group has the necessary inbound/outbound rules to allow access as required.

9. **Review and Launch**: Review the configuration details. Ensure everything is set as desired.

10. **Select Key Pair**:
    - Select “Choose an existing key pair” and choose the key pair from the dropdown.
    - Acknowledge that you have access to the selected private key file.

11. **Click “Launch Instances”** to create the instance.

## Step 2: Access the EC2 Instance

Once the instance is launched, you can access it using the key pair and the instance’s public IP or DNS.

Ensure you have necessary permissions and follow best practices while configuring security groups and key pairs to maintain security for your EC2 instance.

---


Follow these steps to create an IAM role and connect the EC2 instance:

---

# Step 2: Create IAM Role

1. **Search for IAM**:
   - In the AWS Management Console, search for "IAM" in the search bar and click on "Roles".

2. **Create Role**:
   - Click on "Create Role".

3. **Select Entity Type**:
   - Choose "AWS service" as the entity type.

4. **Choose a use case**:
   - Select "EC2" and click "Next".

5. **Set Permissions**:
   - For permission policy, select "Administrator Access" (for learning purposes only). Click "Next".

6. **Name the Role**:
   - Provide a name for the role and click "Create role".

7. **Attach Role to EC2 Instance**:
   - Go to the EC2 Dashboard and select the instance.

8. **Modify IAM Role**:
   - Click on "Actions" -> "Security" -> "Modify IAM role".

9. **Select Role**:
   - Choose the role that was created earlier and click "Update IAM role".

10. **Connect to the Instance**:
    - Connect the instance to VS Code, Mobaxtreme or Putty for accessing it.

---

Here's Step 3 formatted and labeled for your README:

---

# Step 3: Cluster Provision

1. **Clone Repository**:
   ```
   git clone https://github.com/kessiey/super-mario-deploy.git
   ```

2. **Change Directory**:
   ```bash
   cd k8s-mario
   ```

3. **Provide Executable Permission and Run Script**:
   ```bash
   sudo chmod +x script.sh
   ./script.sh
   ```

   This script installs Terraform, AWS CLI, kubectl, and Docker. Check versions:
   ```
   docker --version
   aws --version
   kubectl version --client
   terraform --version
   ```

4. **Change Directory to EKS-TF**:
   ```
   cd EKS-TF
   ```

5. **Initialize Terraform**:
   ```
   terraform init
   ```

   **Note**: Don’t forget to change the S3 bucket name in the `backend.tf` file.

6. **Validate and Plan Terraform**:
   ```
   terraform validate
   terraform plan
   ```

7. **Provision Cluster**:
   ```
   terraform apply --auto-approve
   ```

   Completed in 10 minutes.

8. **Update Kubernetes Configuration**:
   - Make sure to change your desired region.
   ```
   aws eks update-kubeconfig --name EKS_CLOUD --region us-east-2
   ```

9. **Change Directory Back to k8s-mario**:
   ```
   cd ..
   ```

10. **Apply Deployment and Service**:
    **Deployment**:
    ```
    kubectl apply -f deployment.yaml
    ```

    Check the deployment:
    ```
    kubectl get all
    ```

    **Service**:
    ```
    kubectl apply -f service.yaml
    ```

    Check the service:
    ```
    kubectl get all
    ```

11. **Describe Service and Copy LoadBalancer Ingress**:
    ```
    kubectl describe service mario-service
    ```

    Paste the ingress link in a browser to play the Mario game.
---
    http://ada8adc8b087d41558a5495ade0a1ebf-525270150.us-east-2.elb.amazonaws.com/

    
![Screenshot 2024-05-12 194754](https://github.com/kessiey/super-mario-k8s-deploy/assets/122237149/99d02307-5e25-408d-8169-a43db9171d4c)


---


Follow these steps to provision the cluster and deploy the SUPER MARIO GAME. 
---
Enjoy the trip back to 1985! 🎮🍄

