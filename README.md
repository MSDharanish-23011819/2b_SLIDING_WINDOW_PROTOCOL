## 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : DHARANISH MS
## REGISTER NO : 212223240027

## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
# Client :
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr=s. accept()
size=int(input ("Enter number of frames to send"))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
  while(i<len(l)):
   st+=s
   c.send(str(l[i:st]).encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    i+=s
```

# Server :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```

## OUTPUT 
# Client :
![client 2b](https://github.com/MSDharanish-23011819/2b_SLIDING_WINDOW_PROTOCOL/assets/147139454/03a2f3d3-2325-45f8-8cef-4633651397c9)


# Server :
![server 2b](https://github.com/MSDharanish-23011819/2b_SLIDING_WINDOW_PROTOCOL/assets/147139454/6fc719f0-ee8e-4340-8b0a-bc0898bb977f)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
