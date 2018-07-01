# reconnect-fritzbox
Basic idea:
This is an Alfred workflow. It is intended to reconnect your Fritz!Box with one simple Alfred keyword "reconnect". You will also get notified about your changed external IP address.



## Installation:
You install the workflow by simply double clicking the *.alfredworkflow file.

## Usage: 
You simply type "reconnect" in your Aflfred search bar and the process is started.

## How does it work?
1.  Firstly you will get notified about your current external IP address.
2.  Then your Fritz!Box will get a UPnP message to reconnect your internet connection.
3.  Lastly you will get a second notification showing your *old IP* in comparison to your **new IP**

## Troubleshooting:

### Your FRITZ!OS Version is 6.03 or lower:
Please open your Alfred Preferences and find this workflow.
Then double click the BLUE /bin/bash script.
You will find a few lines looking like this:

```bash
curl -s "http://$IP:49000/$varNEW/control/WANIPConn1" -H "Content-Type: text/xml; charset="utf-8"" -H "SoapAction:urn:schemas-upnp-org:service:WANIPConnection:1#ForceTermination" -d "@reconnect.xml" >/dev/null
```

Please change `$varNEW` to `$varOLD`

### Your fritz.box router could not be found:
Please open your Alfred Preferences and find this workflow.
Then double click the BLUE /bin/bash script.
You will find a  line looking like this:

```bash
IP=fritz.box
```
Please find out, what your router's internal IP address is.
e.g. a German default router address would look like: http://192.168.178.1
There is also an Alfred workflow out there to find out your router address: [@packal.org](http://www.packal.org/workflow/router-web-interface)
Now you have to replace `fritz.box`with your actual IP address and save the workflow.
Now you should be ready to go. 

Have fun!
