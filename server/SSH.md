# Secure Shell (SSH)
**SSH or Secure Shell** is a network communication protocol that enables two computers to communicate (c.f http or hypertext transfer 
  protocol, which is the protocol used to transfer hypertext such as web pages) and share data. An inherent feature of ssh is that the communication between the two computers is encrypted meaning that it is suitable for use on insecure networks.

SSH clients will typically support SCP (Secure Copy) and/or SFTP (SSH File Transfer Protocol) for transferring data


## Change SSH port on _Control Web Panel (CWP)_

1. Login to CWP at https://domainname.com:2087 (port 2087 is for a secure connection)
2. Go to Services Config->SSH Configuration
3. This will open for editing the file /etc/ssh/sshd_config
4. Look for the line: 

`Port 22`

and change the port number to something else, like 2211; also remove the # character from the beginning of the line. 
In the end, you will have:

`Port 2211`

5. Click the Save changes button
6.  Go to the Dashboard and restart the SSH server.
7.  Go to Security->CSF Firewall, click the Firewall Configuration button
8.  Look for the # Allow incoming TCP ports section and add your port number to the list.
9. Click the Save changes button
10. Go to Security->CSF Firewall, click the Firewall Restart button
11. Now you will be able to connect to the server via SSH using the new port number



