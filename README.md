# EX01 Developing a Simple Webserver
## Date:22-02-2025

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <body bgcolor="yellow">
         <h1 align="center"><u>device configurations</u></h1>
         <h2 align="center"><i>B Harshala Reddy 24009746</i></h2>
           <ol type="1">
             <li>Device name:	B Harshala Reddy </li>
             <li>Processor:	    13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
             <li>Installed RAM:	16.0 GB (15.7 GB usable)</li>
             <li>Device ID:	    15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
             <li>Product ID:	    00342-42709-01076-AAOEM</li>
             <li>System type:	64-bit operating system, x64-based processor</li>
             <li>Pen and touch:	No pen or touch input is available for this display</li>   
            
           </ol>
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
![Screenshot 2025-04-28 204038](https://github.com/user-attachments/assets/d2230ee0-14d0-428a-b5bb-1b50dbc9e260)


## RESULT:
The program for implementing simple webserver is executed successfully.
