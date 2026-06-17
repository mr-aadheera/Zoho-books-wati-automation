# Zoho Books → WATI WhatsApp Automation

## Overview

Automated WhatsApp notifications using Zoho Books workflows and WATI API.

## Features

- Invoice Creation Notification
- Payment Received Notification
- Outstanding Reminder Automation
- GST Reminder Automation

## Technology Stack

- Zoho Books
- WATI
- WhatsApp Business API
- Python

## Workflow

Invoice Created
→
Zoho Books Workflow
→
API Call
→
WATI
→
WhatsApp Customer

## Step-by-step procedure

- Create a template in WATI
  <img width="794" height="551" alt="image" src="https://github.com/user-attachments/assets/576c32aa-a686-484f-9725-03283da5ea59" />

- NOTE : CREATION OF A TEMPLATE WILL COST YOU WATI WALLET MONEY BASED ON THE COUNTRY YOU LIVE IN. ALSO EXECUTION OF THE TEMPLATE EVERYTIME WILL COST YOU SOME WALLET MONEY approx 15 paise IN INDIA. MAKE SURE THAT YOU HAVE THE CUSTOMER DETAILS READY AND DO SAVE THE CUSTOMER'S WHATSAPP NUMBER ON THE PHONE NUMBER SECTION INSIDE ZOHO BOOKS. ALSO TO ACCESS ZOHO WEBHOOKS AND WORKFLOWS API, YOU NEED TO HAVE A PURCHASED PLAN SUCH AS ZOHO ONE AND ALSO A PLAN IN WATI AS WELL. KINDLY CHECK THE PRICING AND PLANS IN www.wati.io and www.books.zoho.in
- After creation of the template please make sure that your template is approved by Meta.
- Now go to settings→workflow actions→webhooks and create a new webhook.
  <img width="974" height="506" alt="image" src="https://github.com/user-attachments/assets/f5890d33-a728-4947-a5cc-7dd8f2d314f9" />

- name : "The same name of the template inside wati
- module : invoice
- URL & parameters : select "POST" option and paste this same URL : https://live-mt-server.wati.io/1090482/api/v1/sendTemplateMessage
- Below click "add parameter" and in the left box, paste this exact term "whatsappNumber" without quotes.
- in right side box, you can add the placeholder, zoho automatically shows the placeholders. click the phone number option and will give something like this "${CONTACT.CONTACT_MOBILE_PHONE}"
- Go down and add headers, we need two headers.
- left box name it "Authorization" without quotes and parallally right to this paste your wati api token. It will start something like "Bearer xxxxxxxx"
- in the second header left box, paste exactly this without quotes "Content-Type" and parallally to this box paste this exactly without quotes "application/json"
- NOTE: IN SOME CASES ZOHO AUTOMATICALLY HAS THIS HEADER WHEN YOU SELECT BODY AS RAW FORMAT AND JSON. SO NO NEED TO WORRY.
- Now have the authorization type as self authorised.
  <img width="824" height="310" alt="git 3" src="https://github.com/user-attachments/assets/74f6c4e8-938c-46e1-8fba-c7013650203c" />

- proceed to body type and choose "Raw" option and you will see a dropdown next to it. Select JSON and paste the coding in the next file, with appropriate changes given on that code.
- save and proceed to workflow rules tab in zoho.
<img width="843" height="312" alt="image" src="https://github.com/user-attachments/assets/a2700843-8595-4aa0-a76e-9760b6af0ef7" />

- Add new criterion and have the exact stuff as the picture below :
<img width="749" height="292" alt="image" src="https://github.com/user-attachments/assets/18e87e07-eb15-468c-b9fc-41bdfa6c25eb" />

- Click save and proceed to immediate action option near to the criterion you created.
<img width="633" height="338" alt="image" src="https://github.com/user-attachments/assets/b5c4238d-544c-48b9-9bcf-a098603c2a4f" />

- As the above image, select the webhook and the webhook name you created earlier.
- Click save and you are good to go.
- The same procedure applies for the Automatic thanks message to customer through wati. But instead of module invoice you should use customer payment.
<img width="544" height="288" alt="image" src="https://github.com/user-attachments/assets/43c0ec10-fc08-4979-9f85-f51adb2235c2" />

- Have this new workflow rule and
<img width="892" height="513" alt="image" src="https://github.com/user-attachments/assets/9faa1c7e-e82e-4a3a-8547-7dccdd03b947" />

- Use this criterion and proceed.
