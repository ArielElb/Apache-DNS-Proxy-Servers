# Apache-DNS-Proxy-Servers

## Setting up Apache Server:
![image](https://github.com/ArielElb/Apache-DNS-Proxy-Servers/assets/94087682/03e092cb-3aa2-4898-9d04-c512a8f6d9cd)


1. Install Apache by running the following command:
2. Once the installation is complete, open a browser and enter the IP address (127.0.0.1 or localhost) in the address bar. You should see the deployment home page.

3. The deployment page is located in the following path: /var/www/html

4. Navigate to the /var/www/html directory and make any textual changes in the existing HTML file.

5. Refresh the page in the browser to see your changes reflected.

## Analyzing HTTP Traffic with Wireshark:

1. Open Wireshark and capture the traffic.

2. Apply a filter to display only local TCP traffic relevant to the browser (port 80).

3. Analyze the received traffic, focusing on HTTP requests and responses. Take note of the connections, their behavior, opened/closed connections, transferred information, etc.

4. Pay attention to the HTTP traffic and how the protocol handles the elements on the page.

5. Use Wireshark's "Follow" feature to inspect the information of a specific HTTP response.

## Disabling Offload Segmentation Mechanism:

- ethtool -K [interface] tx off sg off tso off

##  Configuring DNS Server:
![image](https://github.com/ArielElb/Apache-DNS-Proxy-Servers/assets/94087682/660f5a6b-ba59-4e7b-b61c-e485b5802fdf)

1. Install DNS server (bind9): sudo apt install bind9

2. Modify options.conf.named file.

3. Restart DNS server: sudo service bind9 restart

## Viewing DNS Cache:

1. Dump DNS cache to db.dump_named: sudo rndc dumpdb -cache

2. Check exported file in /var/cache/bind/.

# Creating an Authoritative DNS Server:

1. Edit named.conf.local file.

2. Create new zone definition.

3. Duplicate and modify db.local to create db.biu.ac.il.

4. Increase serial value in SOA record.

5. Restart DNS server: sudo systemctl restart bind9.service

## Installing Squid Proxy Server:
![image](https://github.com/ArielElb/Apache-DNS-Proxy-Servers/assets/94087682/bc17ef55-3faf-4cd0-977a-c2d6a22728bb)


1. Install Squid proxy server: sudo apt install squid
2. Start squid server: sudo service squid start
3. Configure proxy settings in browser/email.
4. Modify Squid configuration file.
5. Restart proxy server: sudo service squid restart

## Configuring Proxy on Another Computer:

1. Configure second computer to use proxy server.
2. Verify browsing HTTP websites.


