# OCI Fundamentals Workshop

Welcome to OCI Fundamentals Workshop!


pip install -r requirements.txt 


<ins>**Lab 1 – OCI Fundamentals** </ins>

1. **STEP 1 : Create Bucket**

   1. First, make sure you're using the right region - Israel Central (Jerusalem)

      ![drawing](./SS/step1/region.png)
      <!-- <img src="./SS/region.png" alt="drawing" width="2000" height="20"/> -->
   2. Open the OCI navigation menu on top left &nbsp; 

        <img src="./SS/step1/nav_bar_logo.png" alt="drawing" width="20"  display="inline-block" />

   3. Click **Storage** &rarr; **Object Storage & Archive Storage** &rarr; **Buckets**

        ![drawing](./SS/step1/nav_bar_buckets.png)

   4. Click **Create Bucket** (make sure you're in the right compartment)

        ![drawing](./SS/step1/create_bucket_button.png)

   5. Enter a name for your bucket and click **Create**
   (remember the bucket's name, you'll use it later)

        ![drawing](./SS/step1/create_new_bucket.png)

   6. Now before we continue, we need to change the bucket's visibility mode to Public so we'll be able to access it without authorization.

        To do that, click the three poing on the right and then on **Edit Visibility**

        ![drawing](./SS/step1/edit_bucket_visibility_button.png)

   7. Select **Public** and click **Save Changes**

        ![drawing](./SS/step1/change_bucket_visibility.png)

    8. Select **Create Bucket**

        ![drawing](./SS/step1/.png)

   
1. **STEP 2 : Create ADB (Autonomous Database)**

   1. Open the navigation menu and click **Oracle Database** &rarr; **Autonomous JSON Database** 

        ![drawing](./SS/step2/nav_bar_adb.png)

   2. Click **Create Autonomous Database** (make sure you're in the right compartment)

        ![drawing](./SS/step2/create_adb_button.png)

   3. Enter the following:
        
        1. **Compartment:** Select your compartment
        2. **Display name:** Specify a user-friendly description that helps you easily identify the resource
        3. **Database name:** Specify the database name (it must consist of letters and numbers only)
        4. For the workload type, choose **JSON**
        5. For the deployment type, choose **Shared infrastructure**
        6. Keep the database configuration the same
        7. Set the password for the Admin database user in your new database
        8. Choose network access **Secure access from allowed IPs and VCNs only** and select IP notation type **CIDR Block** with the Values **0.0.0.0/0**
        9. Choose **License included** license type
        10. Skip on the Provide contacts section and click **Create Autonomous Database**

    4. Wait until your new Autonomous Database's status changes from Provisioning to Available.

    5. Click **Database actions** and wait for the page to finish initializing and to appear.

        ![drawing](./SS/step2/db_actions_button.png)

    6. Scroll down the Database Actions page until you see Related Services section, then click **ORACLE DATABASE API FOR MONGODB**

        ![drawing](./SS/step2/mongodb_api_button.png)

    7. Copy the connection string for port 27017 and save it - you'll need it later

       Instead of *[user:password@]* enter your database username and password (without the '[]' ) 

       Instead of *[user]* enter your database user

       It should looks like: *mongodb://**user**:**password**@G0D09E...F.adb.il-jerusalem-1.oraclecloudapps.com:27017/**user**?authMechanism...true*

        ![drawing](./SS/step2/connection_string.png)

    8. Scroll down the Database Actions page unti

        ![drawing](./SS/step2/.png)
    
1. **STEP 3 : Open Port 5000 in VCN**

   1. Go to the VCN you've created earlier today by opening the navigation menu and clicking **Networking** &rarr; **Virtual Cloud Networks** and then on your VCN's name.

   2. Under Resources, select **Subnets** and click **Public Subnet-<your_vcn_name>**

        ![drawing](./SS/step3/vcn_public_subnet.png)
    
   3. Under Resources, select **Security Lists** and click **Default Security List for <your_vcn_name>**

        ![drawing](./SS/step3/public_security_list.png)

    4. Click on **Add Ingress Rules**

    5. Enter the following:
        
        1. **Source Type:** Select CIDR
        2. **Source CIDR:** Enter 0.0.0.0/0
        3. **IP Protocol:** Select TCP
        4. **Destination Port Range:** Enter 5000
        5. Click **Save Changes**

        ![drawing](./SS/step3/open_port_5000.png)

    6. Add another Ingress Rule for port 27017

1. **STEP 4 : Git Clone**
   1. Connect to the compute instance you've created earlier today by using the following command on terminal:
    
        *sudo ssh opc@<instance_ip> -i <your_ssh_key_path>.key*

   2. After you connected to your machine, install git by running the following command:    

        *yum install git*

   3. Now clone the git repository by running the following command:    

        *git clone https://github.com/idoashke/OCIFundamentals.git*

    4. For validation, run the command *ls* and check if you see folder named "OCIFundamentals"

    5. Run the following command to install the relevant packs for the app:

        *pip3 install -r requirements.txt*


1. **STEP 5 : Edit Config File**
   1. Open the OCI navigation menu on top left 
   2. Click on Compute à Instances
   3. Click on create instance






