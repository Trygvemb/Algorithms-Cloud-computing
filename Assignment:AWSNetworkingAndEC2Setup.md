# **Assignment: Basic AWS Networking and EC2 Setup**

## **Use Case:**

You are tasked with setting up a simple web application infrastructure in AWS for a small e-commerce platform. This involves setting up the networking (VPC, subnets, security groups, etc.), launching an EC2 instance to serve as a web server, and configuring load balancing and auto-scaling to ensure high availability.

### **Goal:**

By completing this assignment, you'll learn how to:

1. Set up a Virtual Private Cloud (VPC) with proper networking components (subnets, route tables, security groups).
2. Create an EC2 instance to serve a simple web application.
3. Use an Elastic Load Balancer to distribute traffic.
4. Set up Auto Scaling to ensure your application scales according to demand.
5. Practice DNS management using AWS Route 53.

---

### **Step-by-Step Instructions:**

#### **Part 1: Set Up a VPC**

1. **Create a VPC:**
   - Go to the AWS Management Console, navigate to the **VPC** service.
   - Click on **Create VPC**.
   - Give it a name (e.g., `MyVPC`), choose IPv4 CIDR block (e.g., `10.0.0.0/16`).
   - Leave the rest as default and click **Create**.

2. **Create Subnets:**
   - Navigate to **Subnets** under the VPC dashboard.
   - Create two subnets:
     - **Public Subnet** (e.g., `10.0.1.0/24`) for internet-accessible resources.
     - **Private Subnet** (e.g., `10.0.2.0/24`) for resources that are not publicly accessible.
   - Make sure to assign each subnet to different availability zones for high availability.

3. **Set Up Route Tables:**
   - Navigate to **Route Tables** and create a route table for the VPC.
   - Associate the public subnet with the main route table. Add a route to allow internet traffic (e.g., `0.0.0.0/0` to the Internet Gateway).
   - Create another route table for the private subnet, and keep it without direct internet access.

4. **Create a NAT Gateway:**
   - In the **NAT Gateway** section, create a NAT Gateway for the private subnet.
   - Associate this NAT Gateway with the public subnet, and update the route table of the private subnet to route traffic through the NAT.

---

#### **Part 2: Set Up an EC2 Instance**

1. **Launch an EC2 Instance:**
   - Go to **EC2** in the AWS Management Console and click **Launch Instance**.
   - Choose an Amazon Machine Image (AMI), such as Amazon Linux 2 or Ubuntu.
   - Choose **t2.micro** for a free-tier eligible instance type.
   - In **Configure Instance**, select the **public subnet** and enable the auto-assign public IP option.
   - In **Security Groups**, create a new security group and allow **SSH (port 22)** and **HTTP (port 80)** traffic.
   - Click **Launch** and download the key pair for SSH access.

2. **Install a Web Server on the EC2 Instance:**
   - SSH into the EC2 instance using your key pair:

     ```bash
     ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
     ```

   - Install a web server (e.g., Apache):

     ```bash
     sudo yum update
     sudo yum install httpd -y
     sudo service httpd start
     ```

3. **Verify EC2 Setup:**
   - Access the public IP of your EC2 instance in a browser. You should see the Apache default page.

---

#### **Part 3: Set Up Elastic Load Balancer (ELB) and Auto Scaling**

1. **Create an Elastic Load Balancer:**
   - Go to **Load Balancers** in the EC2 dashboard and click **Create Load Balancer**.
   - Choose **Application Load Balancer** and set it to be internet-facing.
   - Add **HTTP (port 80)** as a listener.
   - Associate the load balancer with the **public subnet**.

2. **Target Group and EC2 Registration:**
   - Create a target group for the load balancer and add the running EC2 instance as a target.
   - Test that the load balancer distributes traffic by accessing the **load balancer's DNS** in your browser.

3. **Set Up Auto Scaling:**
   - Go to **Auto Scaling Groups** in the EC2 dashboard and create a new auto-scaling group.
   - Use the same AMI and instance type as your existing EC2 instance.
   - Set the desired number of instances to 1, minimum to 1, and maximum to 2.
   - Add the auto-scaling group to the target group of the load balancer.
   - Define a scaling policy to automatically launch a new instance when CPU usage exceeds 70%.

---

#### **Part 4: DNS and Route 53 Configuration**

1. **Configure DNS with Route 53:**
   - Go to **Route 53** and create a hosted zone (e.g., `mydomain.com`).
   - In the hosted zone, create a new A record that points to your **Elastic Load Balancer's DNS name**.
   - Optionally, register a domain name and route traffic to your load balancer using this custom domain.

2. **Test DNS Configuration:**
   - After setting up DNS, wait for propagation and test accessing your web application using the domain name.

---

### **Summary:**

- **Part 1**: You’ll set up basic networking using a VPC with subnets, route tables, and a NAT gateway.
- **Part 2**: You’ll launch a secure EC2 instance, install a web server, and confirm it's reachable via the internet.
- **Part 3**: You'll configure an Elastic Load Balancer and Auto Scaling for better traffic handling and reliability.
- **Part 4**: You'll configure DNS using Route 53 to route traffic to your web application using a domain name.

### **Next Steps:**

- If this setup works well, try scaling it by adding more instances to the auto-scaling group or adjusting the load balancer's rules.
- You can also explore advanced AWS services, such as S3 for file storage or RDS for database management.

Let me know if you need further clarifications!
