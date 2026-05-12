# 2a_Stop_and_Wait_Protocol

## DATE:11/05/2026
## NAME:PRADEEPA B
## REG:212225040308

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

### CLIENT.PY
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("Enter a data: ")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
    print(ack)
    continue
   else:
    c.close()
    break
```
### SERVER.PY
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Received ".encode())

```
## OUTPUT

#### CLIENT.PY
<img width="978" height="385" alt="Screenshot 2026-05-12 100553" src="https://github.com/user-attachments/assets/32a7b6ec-c0a5-494c-8883-e92ffc197f52" />

#### SEVER.PY
<img width="951" height="642" alt="Screenshot 2026-05-12 100548" src="https://github.com/user-attachments/assets/4985fed1-ba19-4fe0-bddb-397d19467c15" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
