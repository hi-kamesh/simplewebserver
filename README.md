# EX01 Developing a Simple Webserver
## Date:23.5.25

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''

<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Layers and Protocols</title>
    
        
</head>
<body>
    <h2>TCP/IP Layers and Protocols</h2>
    <table border="1">
        <tr>
            <th>TCP/IP Layers</th>
            <th>Protocols (Examples)</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>HTTP, RDP, DNS, SMTP, Telnet, SNMP</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>TCP, UDP</td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>ICMP, IGMP, ARP, IP, IPSec</td>
        </tr>
        <tr>
            <td>Network Access Layer</td>
            <td>Ethernet (IEEE 802.3), Token Ring, PPP, Frame Relay</td>
        </tr>
    </table>
</body>
</html>
"""

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/f488b9aa-28f6-4e9b-8668-07830ee97ec9)


## RESULT:
The program for implementing simple webserver is executed successfully.
