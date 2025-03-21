## EX01: Developing a Simple Webserver
## NAME:ILEVARASEN.S
## Date:21/03/2025

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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    from http.server import HTTPServer, BaseHTTPRequestHandler
content="""
<!DOCTYPE html>
<html>
<head>
	<title>Laptop Specifications</title>
	<style>
		table {
			border-collapse: collapse;
			width: 100%;
		}
		
		th, td {
			border: 1px solid #ddd;
			padding: 10px;
			text-align: left;
		}
		
		th {
			background-color: #f0f0f0;
		}
	</style>
</head>
<body>
	<h1>Laptop Specifications</h1>
	<center><table>
		<tr>
			<th>Specification</th>
			<th>Details</th>
		</tr>
		<tr>
			<td>Processor</td>
			<td>11th Gen Intel Core i7-1165G7</td>
		</tr>
		<tr>
			<td>RAM</td>
			<td>16 GB DDR4</td>
		</tr>
		<tr>
			<td>Storage</td>
			<td>512 GB SSD</td>
		</tr>
		<tr>
			<td>Graphics Card</td>
			<td>NVIDIA GeForce MX450</td>
		</tr>
		<tr>
			<td>Display</td>
			<td>14-inch Full HD (1920x1080)</td>
		</tr>
		<tr>
			<td>Operating System</td>
			<td>Windows 11 Home</td>
		</tr>
		<tr>
			<td>Battery Life</td>
			<td>Up to 8 hours</td>
		</tr>
		<tr>
			<td>Weight</td>
			<td>1.5 kg</td>
		</tr>
	</table></center>
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
httpd= HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
</body>
</html>

```

## OUTPUT:

![Screenshot 2025-03-21 085315](https://github.com/user-attachments/assets/f40750f8-7dbc-47c1-ad29-5f10f60163cb)

![Screenshot 2025-03-21 085616](https://github.com/user-attachments/assets/9cbec824-dcf9-4650-89b1-94d3a02f24b2)


## RESULT:
The program for implementing simple webserver is executed successfully.
