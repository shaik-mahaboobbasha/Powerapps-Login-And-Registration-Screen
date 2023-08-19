# Powerapps-Login-And-Registration-Screen

![](https://miro.medium.com/v2/resize:fit:2000/format:webp/1*ri_IQr_oyxf2s7wx8enzGg.png)

This is a user-friendly power app user registration and login screen designed to have some features that could be required in real-life use cases. Those features include;
* #### **Password validation:**
  Ensuring that passwords include uppercase, lowercase, numbers, and symbols.

* #### **Unique username and email address:**
  Making sure that each user has a distinct username and email.

* #### **Gmail account requirement:**
  Allowing only Gmail accounts for registration.

* #### **Email confirmation code:**
  Sending a code for email confirmation that expires after 5 minutes.

* #### **Password recovery:**
  Enabling users to recover their accounts if they forget their passwords.

## Follow these steps to create the SharePoint lists
#### Step 1:
Create a SharePoint list with the name **LoginDemo** using the column names as seen below. All columns are single-line text fields. The **Title** field can be set to **Not required** in the list settings. To do this, click on the **gear icon** at the top right of the Sharepoint list, then click **List setting**, scroll down and click **Title**. Locate the option **Require that this column contains information** and select the **No** radio button. Scroll down and click **OK**.
![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*tyw60I-bp8UHyNGIOXB5Bw.png)

#### Step 2:
Create another SharePoint list with the name **LoginRecords** using the column names as seen below. The **User** column is a single-line text field, while the **LoginTime** and **LogoutTime** columns are **Date** fields. The **Title** field must be set to **Not Required** in this case. 

![](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*DNDJT6zlGQu0dxtiJkHzKA.png)


## Follow these steps to upload the app

#### Step 1:
Download the **Login and Registration Screen.zip** file above.

#### Step 2:
Navigate to the Power app portal and click on **Apps**

![](https://miro.medium.com/v2/resize:fit:528/format:webp/1*RZjFVOWPbgEmx5-_JWWgFQ.png)

#### Step 3:
Click **Import canvas app**

![](https://miro.medium.com/v2/resize:fit:1474/format:webp/1*O-lgW7traz-mYqDxYVeraw.png)

#### Step 4:
Click **Upload** and wait some minutes for the upload to be completed.

![](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*YDcAT2GFQNSFvFxw1t599A.png)

#### Step 5:
Click **Import**.

![](https://miro.medium.com/v2/resize:fit:4800/format:webp/1*IOj8gfKjPIrN6s39U8BOTQ.png)


