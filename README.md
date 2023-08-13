# Powerapps-Login-And-Registration-Screen

![](https://miro.medium.com/v2/resize:fit:2000/format:webp/1*ri_IQr_oyxf2s7wx8enzGg.png)

# Features include

1. **Password validation:**
Ensure passwords include uppercase, lowercase, numbers, and symbols.

2. **Unique username and email address:**
Ensure users have distinct usernames and emails.

3. **Gmail account requirement:**
Ensure only Gmail accounts for registration.

4. **Email confirmation code:**
   Send confirmation code that expires after 5 minutes.

5. **Password recovery:**
Enable users to recover their accounts if they forget their passwords.


# When can a power app have a login screen?
A Powerapp login screen allows users to enter unique identifier information, usually a username and password before they can access an application. If that username and password validations are correct, then the app will open otherwise it will give a notification error. However, knowing that an Office 365 authentication is required to access the Power Apps portal, it's therefore important to understand why an additional login or registration screen might be useful.

Rejoice Stores is a shopping mall that plans to employ 15 sales personnel who would run different shifts to attend to customers. The management of Rejoice Stores has also decided to build their **Purchase Order Application** using power apps due to its several benefits. Unfortunately, the need to track activities on the purchase order app would mean that all **15 sales representatives would be provided with individual Office365 user accounts**, excluding user accounts for other intended members of staff but this would lead to an increase in overhead cost. However, in a bid to reduce costs, there is an idea to provide all **15 sales representatives with a single Office 365 user account** that they can use to access the purchase order and other necessary applications.

In meeting the requirement of Rejoice Stores, there is a need to ensure that the purchase order and every one of their applications must still be able to track every user and essential activity.

New users are required to register or sign up on the app by providing the required information. If this information passes the validation tests, the app navigates to another screen where users are required to confirm their registration using a code sent to their email address. This is to ensure that every user has a valid email for authentication and other activities.

# Data Connections
1. Create a SharePoint List named **LoginDemo** that stores users' records. Below are the columns to be created. All columns should be a **single line of text**.
* Title (I used SharePoint's title column for the User FullName)
* UserName
* Password
* EmailAddress

2. Add the **Gmail connector** to power apps.

# Steps
![](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*vo-coBCLfaUscPcnzycK5g.png)

1. Add two blank screens to the canvas and name the first screen the **Home Screen**. Paste the below codes in the **onVisible** and **Fill properties** of the **Home Screen**.

**OnVisible:**

` Set(gblShowErrorImage, false );
   ClearCollect(
      colMenuTable,
      {
          Name: "Log in",
          Value: 1
      },
      {
          Name: "Register",
          Value: 2
      },
      {
          Name: "Forgot Password",
          Value: 3
      }
   );`

**Fill:**

`ColorFade( RGBA(22, 255, 89, 1), 90%)`

2. Add a **horizontal container** to the home screen and set its properties to the values below. This container should cover the entire width and height of the screen.

* **Justify:** `Center`
* **Align:** `Center`
* **Width:** `Parent.Width`
* **Height:** `Parent.Height`
* **Gap:** `15`
* **Fill:** `Transparent`

3. Add **two non-responsive containers** into the vertical container created in Step 1 and set their properties to the values provided below.
* **Height:** `720`
* **Align in container:** `Set by container` and `Center`
* **Flexible width:** `Off`
* **Width:** `650`
* **All paddings:** `0`
* **Border radius:** `8`
* **Drop shadow:** `Bold`

4. Add an **HTML Control** to the left-sided container and insert the code below into its **text property**. Set its **Height** and **Width** to desired values and add a desired image or background colour for the container background as shown in the image above.

**HTML Text Property:**

`<div style= 'padding:15px;height:100px; width: "&Parent.Width &"px;  
text-align:center; font-size:4.5em; font-family: Trebuchet MS; 
font-weight:900'>Application Registration Demo</div>`

5. Add a **blank vertical gallery** into the left-sided container as seen above and name it **MenuGallery**. Also, add a **button control** to the gallery template and adjust their **X** and **Y** properties to achieve a similar appearance to what is displayed above, then use the values provided below to set the other properties.

* **Gallery Items:** `colMenuTable`
* **Gallery On Select:**
  `Switch(ThisItem.Name, "Log in", UpdateContext({locPasswordError: false}); Set(gblBlankEntry,false), "Register", UpdateContext({locUsernameError: false}); UpdateContext({locPasswordError: false});)`
* **Button Text:** `ThisItems.Name`
* **Button Fill:** `ColorFade(
      Switch(
          ThisItem.Name,
          "Log in",
          RGBA(
              24,
              156,
              21,
              1
          ),
          "Register",
          RGBA(
              26,
              26,
              26,
              0.6
          ),
          "Forgot Password",
          Color.OrangeRed
      ),
      -10%
  )`
