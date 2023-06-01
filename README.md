# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# DATE : 21-03-2023
# Developed by : Lavanya S
# Reg no: 212221220030
# AIM :
To write a python program to perform sliding window protocol.

# ALGORITHM :
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
6.Stop the program
# PROGRAM :
# CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
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
# SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
    ```
# OUTPUT :
# CLIENT:

![image](https://github.com/LavanyaSIT/EX-3/assets/130207418/ced46e6d-06cc-4d07-94a9-689f9ce71df8)


 # SERVER:
![image](https://github.com/LavanyaSIT/EX-3/assets/130207418/2b7caae8-7aab-4a42-8997-8221fec9c85d)


 # RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

