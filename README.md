# Check_MK WhatsApp notification
<br>

## COMPATIBILITY
- Check_MK RAW version 1.6.0_p18 
- Check_MK RAW version 2.1.0p4
- Should also work with other versions of Check_MK


## EXAMPLE
Notifications are usually sent via a WhatsApp group. Here is an example of how a WhatsApp notification is structured.

<img src="images/WhatsApp_notification_example.png" alt="WhatsApp notification example" width="100%"/>

## REQUIREMENTS
In order for Check_MK to send alerts (notifications) to the WhatsApp Messenger, we need

* WhatsApp line
* url api whatsapp and port
* WhatsApp API token
* a WhatsApp Chat- or Group-ID

## Creating WhatsApp API Key:

To use this shipment, it is necessary to contract the service.

To hire, visit https://www.netizap.app/

There are a lot of good instructions for this on the Internet, so this is not part of this documentation.

## INSTALLATION
Change to your Check_MK site user
```
su - mysite
```

Change to the notification directory
```
cd ~/local/share/check_mk/notifications/
```

Download the WhatsApp notify script from Git repository
```
git clone https://github.com/welligtonalves/check_mk-whatsapp-notify .
```

Give the script execution permissions
```
chmod +x check_mk_WhatsApp-notify.sh
```

## CHECK_MK CONFIGURATION
### CHECK_MK VERSION 2.0.0 AND ABOVE
Now you can create your own alarm rules in Check_MK.

```Setup → Events → Notifications```

First create a clone of your existing mail notification rule

<img src="images/global_notification_rules_create_v2.png" alt="Create clone" width="100%"/>

* Change the description (e.g. Notify all contacts of a host/service via WhatsApp)
* The notification method is "Push Notification (by WhatsApp)"
* Select option "Call with the following parameters:"
* As the first parameter we set the WhatsApp line (API number provided)
* The second parameter is the WhatsApp destiny WhatsApp line / Group-ID
* The third parameter is the api port WhatsApp
* The fourth parameter is the api key WhatsApp

<img src="images/create_new_notification_rule_for_whatsapp.png" alt="Adjust settings" width="100%"/>

<br>

## CONTRIBUTIONS
* Thank you for the excellent code optimization contributions and additional information [ThomasKaiser](https://github.com/ThomasKaiser).
* Best regards to [Jonathan Barratt](https://github.com/reduxionist) in Bangkok and many thanks for adding emojies to the module.

## LICENSE
checkmk-telegram-notify and all individual scripts are under the BSD 3-Clause license unless explicitly noted otherwise. Please refer to the LICENSE