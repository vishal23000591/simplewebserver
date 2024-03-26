# EX01 Developing a Simple Webserver
## Date:

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
content="""

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1 {
            color: blueviolet;font-size: 50px;font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        }
        h2 {
            color: brown;font-size: 20px;font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;

        }
    </style>
</head>
<body style="background-image: url('pleasant.avif'); background-size: cover;">
    
    <center><form  method="get">
        <h1>Enter your Personal details</h1>
        <input type="text" minlength="3" maxlength="30" required name="fname" placeholder="First Name"> <br>
        <input type="text" name="lname" placeholder="Last Name"><br>
        <input type="password"  name="pwd1"  placeholder="Password" pattern="[A-Za-z0-9]" title="Proper ah fill pannu pa thambi"><br>
        <input type="email" name="Email Address" placeholder="Email Address" ><br>
        <input type="email" id="email1" name="Alternate Email Address" placeholder="Alternate Email Address" pattern="[a-z0-9]+@[a-z0-9.\-]+-.[a-z]{2,4}&" title="Correct aana email id podu pa"><br>
        <input type="number" name="Phone" min="6000000000" max="9999999999" placeholder="Phone Number"><br>
        <h2>DOB: <input type="date" name="Date" ></h2><br>
        Gender: <input type="radio" name="gender" value="M">Male <br>
        Gender: <input type="radio" name="gender" value="F">Female <br>
        Electives: <input type="checkbox" name="Python" >Python Programming<br>
        Electives: <input type="checkbox" name="C" >C Programming<br>
        Electives: <input type="checkbox" name="C++" >C++ Programming<br>
        Electives: <input type="checkbox" name="Java" >Java Programming<br>
        Electives: <input type="checkbox" name="Django" >Web Development<br>
        Course: <select name="course" >
            <option value="Select">-----Select any course-----</option>
            <option value="CSE">Computer Science and Engineering</option>
            <option value="CSE(IoT)">Computer Science and Engineering(Internet of Things)</option>
            <option value="AIDS">Artificial Intelligence and Data Science</option>
            <option value="AIML">Artificial Intelligence and Machine Learning></option>
        </select><br>
        <input type="submit" value="Save">
        <input type="reset" value="Clear All">


    </form>
</center>
</body>
</html>

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','test/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd=HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![Screenshot 2024-03-26 152947](https://github.com/vishal23000591/simplewebserver/assets/147139719/81bf0ac8-ad6a-45f4-b50e-921cf92a9ddd)


![alt text](<Screenshot 2024-03-24 171033.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
