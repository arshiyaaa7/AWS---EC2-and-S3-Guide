# AWS – EC2

## 📌 What is AWS?
**Amazon Web Services (AWS)** is a cloud computing platform provided by Amazon.  
It offers a variety of services such as computing power, storage, networking, and databases, enabling you to build and scale applications without owning physical servers.  

## 📌 What is EC2?
**Amazon Elastic Compute Cloud (EC2)** is a service that provides virtual servers (called *instances*) in the cloud.  
With EC2, you can run applications just like you would on a physical computer, but with the flexibility to scale up or down as needed.  

**Key Benefits:**
- Pay-as-you-go pricing.
- Launch servers in minutes.
- Scale computing capacity easily.
- Choose from various operating systems and configurations.

## 📌 What is an AMI?
**Amazon Machine Image (AMI)** is a template used to create EC2 instances.  
It contains the operating system, application server, and applications required to start your instance.  

Examples of AMIs:
- Ubuntu 24.04 LTS
- Amazon Linux 2
- Microsoft Windows Server

## 📌 What is a Key Pair?
A **Key Pair** is used to securely connect to your EC2 instance.  
It consists of:
- **Public Key** (stored on AWS)
- **Private Key (.pem file)** (downloaded and stored locally by you)

⚠️ **Important:** Keep your `.pem` file safe and never share it publicly.  
If you lose it, you cannot connect to your instance.

## 📌 What is a Security Group?
A **Security Group** acts as a virtual firewall for your EC2 instance, controlling inbound and outbound traffic.  

Example rules:
- Allow SSH (port 22) for Linux instances.
- Allow HTTP (port 80) for web servers.
- Allow HTTPS (port 443) for secure web servers.

## 🚀 Steps to Launch an EC2 Instance

### **Step 1: Launch Instance**
1. Sign in to the AWS Management Console.
2. Navigate to **EC2** service.
3. Click **Launch Instance**.
4. Enter a **Name** for your instance.
<img width="698" height="372" alt="Launch" src="https://github.com/user-attachments/assets/3ed88622-b03d-446b-ad08-b88465162599" />


### **Step 2: Choose AMI**
1. Under **Application and OS Images**, select your desired operating system (e.g., Ubuntu 24.04).  


### **Step 3: Choose Instance Type**
1. Select an instance type (e.g., `t2.micro` for free tier).  
<img width="698" height="389" alt="Instance type" src="https://github.com/user-attachments/assets/1b38ad08-de38-4f72-97d9-389a3ea32115" />


### **Step 4: Create/Select a Key Pair**
1. Under **Key Pair (Login)**, choose:
   - **Create a new key pair** if this is your first time.
   - Enter a name for your key.
   - Choose `.pem` format (Linux/Mac) or `.ppk` (Windows with PuTTY).
2. Download the private key file and store it securely.
<img width="698" height="370" alt="Key Pair" src="https://github.com/user-attachments/assets/1eca4072-fe65-4a51-be1a-f30eb9a32ae8" />


### **Step 5: Configure Security Group**
1. Create a new Security Group or select an existing one.
2. Add inbound rules:
   - SSH (port 22) for Linux.
   - RDP (port 3389) for Windows.
3. Review outbound rules (default allows all traffic).  

### **Step 6: Review and Launch**
1. Review your settings in the summary.
2. Click **Launch Instance**.
3. Wait until the status shows **Running**.  
<img width="698" height="374" alt="Success" src="https://github.com/user-attachments/assets/c9136b69-7363-4a91-a4f0-a84a3c380f63" />

### **Step 7: Connect to Your Instance**

After launching your EC2 instance, you can connect to it in two ways:  

- **Using SSH (Linux/Mac):** Open a terminal, navigate to the folder containing your `.pem` file, set the correct permissions, and then run the SSH command to log in to your instance.  

- **Using AWS EC2 Instance Connect:** From the AWS Management Console, select your instance and click **Connect**. Choose **EC2 Instance Connect** and click **Connect** again to open a browser-based terminal.  

⚠️ Always keep your private key secure and avoid sharing screenshots that display unblurred IP addresses or usernames.

---

# AWS – How S3

## 📌 What is S3?
**Amazon Simple Storage Service (S3)** is an object storage service that allows you to store and retrieve any amount of data from anywhere.  
It’s commonly used for backups, file hosting, static website hosting, and storing application data.

**Key Benefits:**
- Highly scalable storage.
- 99.99% availability.
- Access control with permissions.
- Versioning support for file changes.

## 🚀 Steps to Create and Use an S3 Bucket

### **Step 1: Open S3 Service**
1. Sign in to AWS Management Console.
2. Search for **S3** in the search bar and click the service.

### **Step 2: Create a Bucket**
1. Click **Create bucket**.
2. Enter a **unique bucket name** (S3 bucket names must be globally unique).
3. Choose the AWS Region where the bucket will be created.
4. Leave default settings or enable **Versioning** if required.
5. Click **Create bucket**.  
<img width="698" height="371" alt="B1" src="https://github.com/user-attachments/assets/e01d3eef-08fb-410f-b041-38643c57f100" />

### **Step 3: Upload Files**
1. Open the bucket you just created.
2. Click **Upload** → **Add files**.
3. Select files from your local system.
4. Click **Upload** to store them in S3.
<img width="1599" height="859" alt="file b2" src="https://github.com/user-attachments/assets/d8060c3a-39f1-4189-b869-778bb30824c7" />

### **Step 4: Manage Permissions**
1. Select the file you uploaded.
2. Go to **Permissions** tab.
3. Adjust access settings:
   - Private (default)
   - Public read access (for sharing)
4. Save changes.  

### **Step 5: Access Your File**
- Copy the **Object URL** from the file details.
- Paste it into your browser to view/download the file (if it has public access).  
<img width="1599" height="862" alt="success b" src="https://github.com/user-attachments/assets/470cf7a1-eb2a-4f0c-adac-5d1a9a27dde5" />

## 🛡 Notes
- Use **Versioning** to maintain a history of file changes.
- Enable **Bucket Policies** or **IAM roles** to control access for users and applications.
- Always delete unused files to reduce storage costs.

