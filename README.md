## EX01 Developing a Simple Webserver
## Date: 23.03.2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
Step 1: HTML content creation.

Step 2:Design of webserver workflow.

Step 3:Implementation using Python code.

Step 4:Serving the HTML pages.

Step 5:Testing the webserver.

## PROGRAM:
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>Top Software Companies</title>
</head>
<body align="center">
<caption>Top 5 software companies</caption>
<table>
<table border="1" cellspacing="2" cellpadding="2" align="center">
<tr>
                <th>Rank</th>
                <th>Company Name</th>
                <th>Revenue(billion dollars)</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Microsoft</td>
                <td>203.08</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Oracle</td>
                <td>46.07</td>
            </tr>
            <tr>
                <td>3</td>
                <td>SAP SE</td>
                <td>32.97</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Salesforce</td>
                <td>30.29</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Adobe</td>
                <td>17.61</td>
</table>
</body>
</html>

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
~~~
## OUTPUT:

![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/8826e59b-55f6-4233-bfae-44f888697b73)

![image](https://github.com/niranjanadevi-s/simplewebserver/assets/141748873/6fc34cab-c46c-4c39-abc7-e103242db1f2)

## RESULT:
The program for implementing simple webserver is executed successfully.



