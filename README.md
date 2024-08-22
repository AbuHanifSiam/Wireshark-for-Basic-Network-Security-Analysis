# Wireshark-for-Basic-Network-Security-Analysis
This is a course conducted by Coursera. Here is my certificate.
![Project certificate](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/7d86608ea5d10f0b2bc6c276230e7764c994defb/Wireshark%20for%20Basic%20Network%20Security%20Analysis.pdf)

# Generate and Capture Radius Traffic
In this segment, it will show how to capture on a port. By using the **Public Radius Server**, this task shows how to capture the authentication request and how to check encrypt and decrypt data. So the steps are:
1. On this website, https://idblender.com/tools/public-radius, first set a username and password to check how to authenticate using Wireshark. <br><br> ![Public RADIUS Server](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/27c057784c8bdcf2fadc34cec1f26df04abd4700/wireshark_pictures/RADIUS%20server.png)
2. Open the Wireshark and in the filter section, search for port 1812 and double-click on Ethernet. The RADIUS server is running in port 1812, the Wireshark only captures what is happening in port 1812. It will start capturing and it is not showing any packet capture.<br><br>![](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/27c057784c8bdcf2fadc34cec1f26df04abd4700/wireshark_pictures/wireshark%20interface.png)
3. To capture some packets, we need to send a request to the server using port 1812. To send the requests, we used *NTRadPing Test Utility* software. This software sends requests to different servers. Download and open this software. Set all the criteria there. And then send a request to the server. Now Wireshark shows capture. <br><br> ![NTRadPing Test Utility](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/27c057784c8bdcf2fadc34cec1f26df04abd4700/wireshark_pictures/NTRadPing%20Test%20Utility.png)
4. At first send a request using the correct authentication and again send a request with the wrong authentication. No click on the access accept packet and analyze it. 
5. In the Access Request packet we can see the username and the password is encrypted. But we can decrypt it. Go to edit and then preferences. Search for protocols and then RADIUS and set the shared secret key secret that we set in the NTRadPing software. Now the password will be decrypted. <br><br>![Encrypt Wireshark Password](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/27c057784c8bdcf2fadc34cec1f26df04abd4700/wireshark_pictures/encrypt%20packet.png)
<br><br>![Decrypt Wireshark Password](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/27c057784c8bdcf2fadc34cec1f26df04abd4700/wireshark_pictures/decrypt%20packet.png)

<br>
This is how we can analyze the authentication packets and also check the username and password if the protocol and security are very weak. 

# HTTP Form-Based Authentication and DNS
In this segment, we will check if the form-based authentication is safe or not. Also, the DNS protocol gives the encrypted data or decrypted data. 
To check this first go to this website http://testing-ground.webscraping.pro/login?mode=login and open the wireshark. As HTTP use port 80, set the capture port 80 in Wireshark and start the capture. Go to the website and log in with credentials. Back to the Wireshark and stop capturing packets. After that select the login packet and there we can see the available credentials and those that are not in hashing format. <br><br>![Decrypt Packet](https://github.com/AbuHanifSiam/Wireshark-for-Basic-Network-Security-Analysis/blob/909c172423884446ee0a1ff54d33ee73766e9c54/wireshark_pictures/decrypt%20packet_4.png) 
It's available there in simple text format. That is why HTTP Form-Based authentication is the weakest authentication system.

Again if we capture the DNS packet, we can see all the details given in the packet. So it's also not safe to use. 

