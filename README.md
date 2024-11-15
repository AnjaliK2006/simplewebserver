# EX01 Developing a Simple Webserver
## Date: 08/10/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <body bgcolor="Red">
    <h1 align="center">LAPTOP PROPERTY(Anjali-24900073)</h1>
   <ol>
<li>Device name	LAPTOP-CRQ6CEFC</li>
<li>Processor	AMD Ryzen 5 7520U with Radeon Graphics            2.80 GHz</li>
<li>Installed RAM	16.0 GB (13.8 GB usable)</li>
<li>Device ID	0C4FC7B6-2C3F-4222-868F-63144033A08B</li>
<li>Product ID	00342-42591-60567-AAOEM</li>
<li>System type	64-bit operating system, x64-based processor</li>
<li>Pen and touch No pen or touch input is available for this display</li>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```


## OUTPUT:
![alt text](<Screenshot 2024-11-12 093324.png>)
![alt text](<Screenshot 2024-11-12 093734.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
