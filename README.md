# EX01 Developing a Simple Webserver
## Date: 23.03.2024

## AIM:
To develop a simple webserver to serve html pages.

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
~~~

from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Webserver</title>
</head>
<body>
    <h1>Top 5 Revenue Companies</h1>
    <ol>
        <li>Apple</li>
        <li>Google</li>
        <li>Amazon</li>
        <li>Samsung</li>
        <li>TATA</li>
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

server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()

~~~
## OUTPUT:
![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/923c41ae-9680-48c9-87b4-69a4da64e89a)
![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/cf30e413-1a9a-4c0b-b710-df5308ccbb8e)




## RESULT:
The program for implementing simple webserver is executed successfully.

![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/e0fd9ef9-9099-492b-9641-4aecf08efc5f)

![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/dfb9923e-dd0d-4dd6-926b-9dcc4755416b)


