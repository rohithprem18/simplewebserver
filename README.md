# EX01 Developing a Simple Webserver
## Date: 26.02.2024

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
    <title>TOP COMPANY </title>
</head>
<body>
    <table border="1" cellspacing="2" align="center" height="300" width="450">
	<caption> <b>TOP SOFTWARE COMPANIES </b></caption>
        <tr>
            <td bgcolor="cyan" align="center" >Rank</td>
            <td bgcolor="cyan" align="center">Company</td>
            <td bgcolor="cyan" align="center" >Revenue per employee</td>
            <td bgcolor="cyan" align="center">Headquarters</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#1</td>
            <td bgcolor="yellow" style="color:red;" align="center">Apple</td>
            <td bgcolor="yellow" style="color:red;" align="center">$1,859,000</td>
            <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#2</td>
            <td bgcolor="yellow" style="color:red;" align="center">Facebook</td>
            <td bgcolor="yellow" style="color:red;" align="center">$1,621,000</td>
            <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#3</td>
            <td bgcolor="yellow" style="color:red;" align="center">Alphabet</td>
            <td bgcolor="yellow" style="color:red;" align="center">$1,253,000</td>
            <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#4</td>
            <td bgcolor="yellow" style="color:red;" align="center">VeriSign</td>
            <td bgcolor="yellow" style="color:red;" align="center">$1,154,000</td>
            <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#5</td>
            <td bgcolor="yellow" style="color:red;" align="center">Visa</td>
            <td bgcolor="yellow" style="color:red;" align="center">$1,062,000</td>
            <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>

        <tr>
            <td bgcolor="yellow" style="color:red;" align="center">#6</td>
            <td bgcolor="yellow" style="color:red;" align="center">Mastercard</td>
            <td bgcolor="yellow" style="color:red;" align="center">$906,000</td>
	    <td bgcolor="yellow" style="color:red;" align="center">USA</td>
        </tr>
    </table>
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
![alt text](<Screenshot (16).png>)
![alt text](<Screenshot (17).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
