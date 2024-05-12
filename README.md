# super-mario-deploy
Sure, here's the text reformatted and relabeled for a README on GitHub:

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

Feel free to adjust the formatting or wording as needed for your README on GitHub!
