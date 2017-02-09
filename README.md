# Omron-GUI
Omron V680S-HMD63 Interface

This is a small project to interface the Omron V680S-HMD63 commercial RF read/write module with a Windows computer. The project encompasses
a library for the computer-module interface and a py file for a simple GUI. Much of the code is still very dirty and it was a "quick fix"
to have the project up and running. 

Update to v0.0.2
  GUI:
    Bug fixes to disconnected device:
    Function stop(sock) did not work as intended. Time outs would trigger stop(sock) as a result of line 72 in v0.0.1 always returning
    False. The function was rewritten using try/except and writing to the device. If the device is disconnected or powered off then the 
    function will return False. If the query is received then it will return True.

Update to v0.0.3
  GUI:
    Added default file extension in browse directory to be .xml. fileOpts variable added as global variable under initialize function.
    Changed column span of start button to 1 for future implementation of status button.
    Fixed bug where browsing more than once would not delete the old entry in directory and instead add to the string.
    Fixed bug where changing the file directory after having a valid directory did not update filename variable. filename variable 
    assignment added to the beginning of reader function. filename variable assignment removed from browse_dir function.
  Interface:
    Changed timeout for reading/writing to 3s from 5s.

Update to v0.0.v4
  GUI:
    Fixed bug where exiting file directory deletes the entry. Closing file directory with a string in entry no longer deletes it. 
    Added a counter for the number of RF tags successfully written. Declared as self.counter. Counter increments upon successful
    execution of self.reader.
    Added additional window pop-up for quit verification. Window pops up upon hitting quit button or close.
  Interface:
    Changed timeout for reading/writing to 2s from 3s.
    Added timeout and timeout error to setTCP_IP() function.
