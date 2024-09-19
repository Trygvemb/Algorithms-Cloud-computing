Here is the revised version of the assignment with the addition of **How to Set Up HTTPS on Your EC2 Instance** after Part 2:

---

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
   - Choose Linux Amazon Machine Image (AMI).
   - Choose **t2.micro** for a free-tier eligible instance type.
   - In **Configure Instance**, select the **public subnet** and enable the auto-assign public IP option.
   - In **Security Groups**, create a new security group and allow **SSH (port 22)** and **HTTP (port 80)** traffic.
   - Click **Launch** and download the key pair for SSH access.

2. **Install a Web Server on the EC2 Instance:**
   - SSH into the EC2 instance using your key pair:

     ```bash
     ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
     ```

     Example: `ssh -i ~/Downloads/MyEC2Key.pem ec2-user@3.123.456.789`

   - Install a web server (e.g., Apache):

     ```bash
     sudo yum update
     sudo yum install httpd -y
     sudo service httpd start
     ```

3. **Verify EC2 Setup:**
   - Access the public IP of your EC2 instance with HTTP in a browser. You should see the Apache default page.
   - Example: `http://your-ec2-public-ip`

---

#### **Part 2.5: Set Up HTTPS on Your EC2 Instance**

Now that you have HTTP set up and running, let's configure **HTTPS** (secure HTTP):

1. **Install `mod_ssl` for Apache**:
   This is required to enable SSL/TLS in Apache.

   ```bash
   sudo yum install -y mod_ssl
   ```

2. **Generate a Self-Signed SSL Certificate** (For testing purposes):
   - Run the following command to generate a self-signed SSL certificate:

     ```bash
     sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/pki/tls/private/selfsigned.key -out /etc/pki/tls/certs/selfsigned.crt
     ```

   - When prompted, fill in details such as country, state, organization, etc.

3. **Configure Apache for SSL**:
   Edit the Apache SSL configuration file:

   ```bash
   sudo nano /etc/httpd/conf.d/ssl.conf
   ```

   - Look for the following directives and set them to point to your self-signed certificate and key:

     ```
     SSLCertificateFile /etc/pki/tls/certs/selfsigned.crt
     SSLCertificateKeyFile /etc/pki/tls/private/selfsigned.key
     ```

4. **Update Firewall (Security Groups)**:
   Ensure that your **security group** allows inbound traffic on port **443** for HTTPS.

   - In the AWS Console, go to **EC2 > Instances > Security Groups** and add a new inbound rule for HTTPS:
     - **Type**: HTTPS
     - **Port**: 443
     - **Source**: `0.0.0.0/0` (for access from anywhere).

5. **Restart Apache**:
   After configuring SSL, restart Apache to apply the changes:

   ```bash
   sudo systemctl restart httpd
   ```

6. **Test HTTPS**:
   - Now, try accessing your EC2 instance with **HTTPS**:

     ```
     https://your-ec2-public-ip
     ```

     Since this is a self-signed certificate, your browser will likely show a warning indicating that the certificate is not trusted. You can bypass this by clicking "Advanced" and proceeding to the site.

---

#### **Part 3: Set Up Elastic Load Balancer (ELB) and Auto Scaling**

1. **Create an Elastic Load Balancer:**
   - Go to **Load Balancers** in the EC2 dashboard and click **Create Load Balancer**.
   - Choose **Application Load Balancer** and set it to be internet-facing.
   - Add **HTTP (port 80)** as a listener.
   - Associate the load balancer with the **public subnet**.

   - **Target Group and EC2 Registration:**
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
   - Propagation can take up to 48 hours
   - After setting up DNS, wait for propagation and test accessing your web application using the domain name.
      - [nslookup.io/](https://www.nslookup.io/) or [dnschecker.org](https://dnschecker.org/) can help check DNS propagation status.

---

### **Summary:**

- **Part 1**: You’ll set up basic networking using a VPC with subnets, route tables, and a NAT gateway.
- **Part 2**: You’ll launch a secure EC2 instance, install a web server, and confirm it's reachable via the internet.
- **Part 2.5**: You’ll set up HTTPS on your EC2 instance using a self-signed SSL certificate.
- **Part 3**: You'll configure an Elastic Load Balancer and Auto Scaling for better traffic handling and reliability.
- **Part 4**: You'll configure DNS using Route 53 to route traffic to your web application using a domain name.

### **Next Steps:**

- If this setup works well, try scaling it by adding more instances to the auto-scaling group or adjusting the load balancer's rules.
- You can also explore advanced AWS services, such as S3 for file storage or RDS for database management.

---

## Finished Assignment

- See website hosted on AWS with EC2 Instance:
   - [Public IPv4 DNS with HTTP](http://ec2-13-55-9-72.ap-southeast-2.compute.amazonaws.com/)
   - [Public IPv4 address with HTTP](http://13.55.9.72/)
   - [Public IPv4 DNS with HTTPS](https://ec2-13-55-9-72.ap-southeast-2.compute.amazonaws.com/)
   - [Public IPv4 address with HTTPS](https://13.55.9.72/)

- See website hosted on AWS with Elastic Load Balancer:
   - [Load Balancer DNS with HTTP](http://mybalancer-1113359172.ap-southeast-2.elb.amazonaws.com/)

- See website hosted on AWS with Route 53: (Not yet available)
   -~~Custom Domain with HTTP myfirstaws.com~~
