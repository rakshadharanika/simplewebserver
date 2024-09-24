# EX01 Developing a Simple Webserver
## Date:9/17/2024
## NAME   : V RAKSHA DHARANKA
## REF NO : 212223230167

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
```html
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
    <title>Laptop Configuration</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
        }
        h2 {
            text-align: center;
            color: #333;
        }
        table {
            border-collapse: collapse;
            margin: auto;
            width: 80%;
            background-color: beige;
        }
        th, td {
            border: 3px solid #333;
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #d3d3d3;
        }
    </style>
</head>
<body>
    <h2>Laptop Configuration</h2>
    <table>
        <tr>
            <th>ITEM</th>
            <th>VALUE</th>
        </tr>
        <tr>
            <td>OS Name</td>
            <td>Microsoft Windows 11 Home</td>
        </tr>
        <tr>
            <td>Version</td>
            <td>10.0.22631 Build 22631</td>
        </tr>
        <tr>
            <td>Other OS Description</td>
            <td>Not Available</td>
        </tr>
        <tr>
            <td>OS Manufacturer</td>
            <td>Microsoft Corporation</td>
        </tr>
        <tr>
            <td>System Name</td>
            <td>BEAST</td>
        </tr>
        <tr>
            <td>System Manufacturer</td>
            <td>LENOVO</td>
        </tr>
        <tr>
            <td>System Model</td>
            <td>81X7</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>x64-based PC</td>
        </tr>
        <tr>
            <td>System SKU</td>
            <td>LENOVO_MT_81X7_BU_idea_FM_IdeaPad 3 14ITLOS</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>11th Gen Intel(R) Core(TM) i3-1115G4 @ 3.00GHz, 2995 Mhz, 2 CoA</td>
        </tr>
        <tr>
            <td>BIOS Version/Date</td>
            <td>LENOVO GCCN26WW, 3/11/2022</td>
        </tr>
    </table>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()


```
## OUTPUT:
![image](https://github.com/user-attachments/assets/248b36e4-80aa-4a29-a376-2150b06453d4)





![image](https://github.com/user-attachments/assets/ca539201-6ea4-4ef4-a0b0-0fde1a0d03d4)


## RESULT:
The program for implementing simple webserver is executed successfully.
