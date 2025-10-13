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


##Javascript Enabled in Webview
Impact: An attacker can inject malicious JavaScript code into the webview activity if its "setJavaScriptEnabled" attribute is set to "true". 

Description: Webview is a web browser that can be built into an application. It is the most commonly used component in the Android ecosystem. It also leads to a number of potential vulnerabilities. JavaScript-enabled web content can expose applications to vulnerabilities like cross-site scripting (XSS). Such vulnerabilities could compromise sensitive user data or even lead to unauthorized access. Despite its extensive use and accessibility, implementing measures such as input validation is crucial to prevent these security issues.

Recommendations: The following recommendations can help secure mobile applications against this vulnerability.
Disable JavaScript execution if not necessary by setting the setJavascriptEnable() function to false. If JavaScript is necessary, only load content from the trusted servers using an encrypted channel such as HTTPS with certificate verification

Reproduction Steps: To reproduce this issue, follow the steps below.
1.	Navigate to AndroidManifest.xml file.
2.	Navigate to com.ianacare.ianacare > util > AdvancedWebView.
3.	Observe that "setJavaScriptEnable" is set to "true" for “package_name.util.AdvancedWebView”.

