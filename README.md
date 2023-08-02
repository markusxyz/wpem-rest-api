# wpem-rest-api

## Python Example for inserting Events

```import requests
import base64

wordpress_user = "ck_xxxxxx"
wordpress_password = "cs_xxxxxxx"
wordpress_credentials = wordpress_user + ":" + wordpress_password
wordpress_token = base64.b64encode(wordpress_credentials.encode())
wordpress_header = {'Authorization': 'Basic ' + wordpress_token.decode('utf-8')}

api_url = 'https://website.com/wp-json/wpem/events'

data = {
    'event_title': 'TEST77777', 
    'event_id': '0',
    'event_type': '41', 
    'event_online': 'no', 
    'event_pincode': '4543', 
    'event_location': 'place', 
    'current_event_banner': 'https://website.com/wp-content/uploads/event-manager-uploads/event_banner/.....png', 
    'event_description': '<p>fdg</p>', 
    'registration': 'dfgf@df.de', 
    'event_registration_email': 'info@xxxyyy.com',
    'event_start_date': '30.08.2023', 
    'event_start_time': '01:00', 
    'event_end_date': '31.08.2023',
    'event_end_time': '01:00',  
    'event_registration_deadline': '',
    'event_manager_form': 'submit-event',
    'step': '0',
    'submit_event': 'Vorschau',
    'event_banner': '',
    'event_video_url': ''


 }
response = requests.post(api_url,headers=wordpress_header, json=data)
print(response._content)
