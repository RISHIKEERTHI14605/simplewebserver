# EX01 Developing a Simple Webserver
## Date:21.03.2024

## AIM:
Develop a webserver to display about the Top five Revenue generating Software Companies.

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
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Top 5 Revenue Generating Companies</u><h1>
<ul>
<li>Apple</li>
<li>Amazon</li>
<li>Microsoft</li>
<li>Samsung</li>
<li>Google</li>
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
![alt text](<Screenshot 2024-03-21 192305.png>)
![alt text](<Screenshot 2024-03-21 192157.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
