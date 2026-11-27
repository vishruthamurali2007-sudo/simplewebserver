# EX01 Developing a Simple Webserver
## Date:27-11-26

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

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
'''
<!DOCTYPE html>
<html>
<head>
    <title>My Simple Webserver</title>
</head>
<body>
    <h1>Name:Vishrutha</h1>
    <h1>Register Number:26016534</h1>
    <h1>My Simple Webserver</h1>
    <h2>Laptop Specifications</h2>
    <p>Operating System: Windows</p>
    <p>My webserver is working successfully!</p>
</body>
</html>
'''
'''
import http.server
import socketserver
import socket
import platform

PORT = 8000

class MyHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        if self.path == '/':
            self.path = '/index.html'
        return http.server.SimpleHTTPRequestHandler.do_GET(self)

with socketserver.TCPServer(("", PORT), MyHandler) as server:
    print("Server started at http://localhost:8000")
    print("Operating System:", platform.system())
    print("Computer Name:", socket.gethostname())
    server.serve_forever()
'''
## OUTPUT:
![alt text](<Screenshot 2026-11-27 102450.png>)

![alt text](<Screenshot 2026-11-27 102521.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
