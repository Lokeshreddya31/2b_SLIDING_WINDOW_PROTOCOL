# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

### Name: LOKESH REDDY A
### Reg.NO: 212223040104
## AIM
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM
### CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size: "))
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

### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### CLIENT:
![Screenshot 2024-04-29 204208](https://github.com/Lokeshreddya31/2b_SLIDING_WINDOW_PROTOCOL/assets/144870682/52dfd1cb-2cc1-487b-9fee-f27a395856c2)

### SERVER:
![Screenshot 2024-04-29 204255](https://github.com/Lokeshreddya31/2b_SLIDING_WINDOW_PROTOCOL/assets/144870682/531d0a6d-7b9b-42ef-87c9-24db3fe0380e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
