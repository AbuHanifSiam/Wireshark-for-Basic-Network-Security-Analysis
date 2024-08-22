# Wireshark-for-Basic-Network-Security-Analysis
This is a course conducted by coursera.

# Genrate and Capture Radius Traffic
In this segment, it will show how to capture on a port. By using the **Public Radius Server**, this task shows how to capture the authentication request and how to check encrypt and decrypt data. So the steps are:
1. In this website, https://idblender.com/tools/public-radius, first set a username and password for checking how to do authenctication using wireshark. ![Public RADIUS Server](image.png)
2. Open the wireshark and in the filter section, search for port 1812 and double click on Etherner. As the RADIUS server are running in port 1812, so the wireshark only capture what is happening in port 1812. It will start capturing and it is not showing any packet capture. 
3. To capture some packets, we need to send request to the server using port 1812. For sending the requests, we used *NTRadPing Test Utility* software. This software send requests to different server. Download and open this software. Set all the criteria there. And then send request to server. Now wireshark shows captures. 
4. At first send request using the correct authentication and again send request with wrong authenticaion. No click on the access accept packet and analyze it.
5. In the Access Request packet we can see the username and password is encrypted. But we can decrypt it. Go to edit and then preferences. Search for portocols and then RADIUS and set the shared secret key secret what we set in the NTRadPing software. Now the password will be decrypted.
6. This is how we can analyze the authentication packets and also check the username and password if the proctocol and security is very weak. 
