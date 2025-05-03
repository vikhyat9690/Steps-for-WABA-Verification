# Register the Phone Number with WhatsApp Business API

## After ensuring the number is unlinked:

### Access Meta Business Manager:

 - Navigate to [Meta Business Manager](https://business.facebook.com/).
 
 - Select your business account.

### Navigate to WhatsApp Business Settings:

 - In the left-hand menu, click on Business Settings.

 - Under Accounts, select WhatsApp Accounts.

 - Choose your WhatsApp Business Account (WABA).

### Add Phone Number:

 - Click on Phone Numbers and then Add Phone Number.

 - Enter the required details, including the display name and region.

 - Verify the number via SMS or voice call.

### Complete Two-Step Verification:

 - Set up a 6-digit PIN for **two-step verification**. This is **mandatory** for managing your WhatsApp Business API account.


 - ![image](https://github.com/user-attachments/assets/4ee20691-885e-48fa-8813-75574c72a6f8)


### Register the Number via API:

 - Obtain your phone_number_id from the WhatsApp Business API setup.

### Make a POST request to register the number:

 ```bash
 curl -X POST https://graph.facebook.com/v19.0/<phone_number_id>/register \
 -H 'Authorization: Bearer <your_access_token>' \
 -H 'Content-Type: application/json' \
 -d '{
   "messaging_product": "whatsapp",
   "pin": "<your_6_digit_pin>"
 }'
 ```
 - Replace <phone_number_id>, <your_access_token>, and <your_6_digit_pin> with your actual values.

 - A successful response indicates that the number is registered.


 ## Phone number Id and whatsapp business account id:

 ![image](https://github.com/user-attachments/assets/0a3b0130-a736-41bf-835b-d6962abb0df7)


## For Access token:

 - Go to the **>System Users > Generate Token > Select App > Duration 60days** in the meta developers site.

 ### Now generate the token and pass in the cURL request:
    
    ```bash -h Authorization: Bearer <your-access-token> ```

  - [Generate Access Token](https://developers.facebook.com/docs/graph-api/system-user)
  - ![image](https://github.com/user-attachments/assets/26c474c0-b887-46e9-8684-f9e18c54e279)


 ## More references :

 - [Meta For Developers: Phone Number](https://developers.facebook.com/docs/whatsapp/cloud-api/phone-numbers/)
 
 - [Meta For Developers: Business Profile](https://developers.facebook.com/docs/whatsapp/cloud-api/reference/business-profiles/)

 - [360dialog: Change Profile Details](https://www.zoko.io/learning-article/change-the-profile-details)
