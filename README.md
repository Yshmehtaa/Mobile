$ frida --codeshare KishorBal/multiple-root-detection-bypass -f YOUR_BINARY 
$ frida --codeshare d3tonator/ssl-and-root-detection-bypass -f YOUR_BINARY
$ frida --codeshare pcipolloni/universal-android-ssl-pinning-bypass-with-frida -f YOUR_BINARY
$ frida --codeshare akabe1/frida-multiple-unpinning -f YOUR_BINARY
$ frida --codeshare dzonerzy/fridantiroot -f YOUR_BINARY
$ frida --codeshare pcipolloni/universal-android-ssl-pinning-bypass-with-frida -f YOUR_BINARY
$ frida --codeshare Q0120S/bypass-ssl-pinning -f YOUR_BINARY

Another  way to bypass SSL Pinning is through download the js file and use that. 
Good read: https://redfoxsec.com/blog/ssl-pinning-bypass-android-frida/

Download the Script from:
https://github.com/themalwarenews/frida_rootandsslbypass/tree/main



##Vulnerabilities.
Mobile Application data handling (Clipboard)

Impact: When typing data into an input field, the clipboard can be used to copy data. The clipboard is accessible system-wide and is, therefore, shared by apps. This sharing can be misused by malicious applications to obtain sensitive data that has been stored in the clipboard.

Description: In Android, the clipboard is shared by all applications and may thus be accessed by any application on the device. This vulnerability involves the potential risk of storing sensitive text, such as passwords or personal information, in the device clipboard. This allows malicious apps to access those sensitive data, posing a security threat to user privacy and confidentiality of the stored information.

Recommendations: The following recommendations can help secure mobile applications against this vulnerability.
Where appropriate, disable copy/paste for areas handling sensitive data. Eliminating the option to copy can help avoid data exposure. Consider whether the user will need to copy/paste data within the app or system-wide, and choose the appropriate type of pasteboard.

Reproduction Steps: The following steps require the use of a runtime mobile exploration tool, such as Objection , powered by Frida . The installation guide for Frida can be viewed here and for Objection can be viewed here.
To reproduce this issue, follow the steps below.
1.	Copy the credentials of the user – "email-id".
2.	Hook the ianacare application to Objection and explore command-
>objection -g application_package_name explore
>android clipboard monitor



