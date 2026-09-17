# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
### echoserver.py
```
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()

    print("Server listening on localhost:65432")

    conn, addr = s.accept()

    with conn:
        print("Connected by", addr)

        while True:
            data = conn.recv(1024)

            if not data:
                break

            print("Received: Adithya NM")

            conn.sendall(data)
```

### echoclient.py
```
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b'Adithya NM')
    data = s.recv(1024)

print('Received', repr(data))
```

## OUTPUT:

### echoserver.py
<img width="1673" height="940" alt="echoserver py" src="https://github.com/user-attachments/assets/51758804-6fe5-4691-bd09-87b6c31e488f" />

### echoclient.py
<img width="1674" height="940" alt="echoclient py" src="https://github.com/user-attachments/assets/ab729c0e-0997-4eac-a584-3494e3149cfa" />


## RESULT:
The program is executed successfully
