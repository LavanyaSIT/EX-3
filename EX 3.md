# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# Date:21/03/2023
# Developed by:LAVANYA S
# Reg.no:212221220030
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
![image](https://github.com/sujathamohankumar/EX-3/assets/130207418/1af3d0de-0c6d-4907-823e-05c67c080ea6)

# SERVER:
![image](https://github.com/sujathamohankumar/EX-3/assets/130207418/c6ac745f-2a3b-4d64-a1b5-478dfb2d6cfa)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.




