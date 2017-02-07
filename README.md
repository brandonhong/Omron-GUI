# Omron-GUI
Omron V680S-HMD63 Interface

This is a small project to interface the Omron V680S-HMD63 commercial RF read/write module with a Windows computer. The project encompasses
a library for the computer-module interface and a py file for a simple GUI. Much of the code is still very dirty and it was a "quick fix"
to have the project up and running. 

Update to v0.0.2
  Bug fixes to disconnected device
    Function stop(sock) did not work as intended. Time outs would trigger stop(sock) as a result of line 72 in v0.0.1 always returning False. The function was rewritten using try/except and writing to the device. If the device is disconnected or powered off then the function will return False. If the query is received then it will return True.
