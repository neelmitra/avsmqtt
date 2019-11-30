![alt text](../images/aws_logo.png)

# Mac : Connect over serial terminal

1. Launch Spotlight by pressing Cmd + Space

2. Type terminal

3. Select the Terminal app

4. In the Terminal window, enter the command: 
    ```
    ls /dev/cu.usb*
    ```
5. In the list of connected devices, look for a device that contains cu.usbmodem*

6. Connect to the USB serial device using the Terminal screen utility by entering the command: 
    ```
    screen /dev/cu.usbmodemXXXXX 115200 -L
    ```

7. Once you are connected , you will see a blank screen , press enter twice and SHELL interface will appear. 
    ```
    SHELL>>
    ```

<span style="color:orange">To end a session in Screen, type Ctrl + A then Ctrl + K. You will be prompted to end the session, press y.</span>

### Continue with [lab2](./lab2.md) now. 


# Linux : Connect over serial terminal

1. Open a new Terminal window. Enter the command: 

    ```
    ls /dev/tty∗
    ```
    
    Then ’/dev/ttyACM0’ is found.

2. In the terminal window, run

    ```
    minicom -s
    ```

3. To configure the ttyACM0 as the default console and other configurations, run

    ```
    minicom
    ```

    The ttyACM0 can be opened successfully and user can input characters by using the minicom.

### Continue with [lab2](./lab2.md) now. 


# Windows : Connect over serial terminal

1. A COM port is enumerated in the Device Manager. If it prompts for CDC driver installation, see the next chapter to install the CDC driver.

2. Open the COM port in a terminal tool, such as Putty / Tera Term.

3. Type characters. The characters are echoed back from the COM port.

## Drivers 
1. if issues with drivers, please refer to detailed [instructions](https://alexa-reinvent.s3.amazonaws.com/readme.pdf) here


### Continue with [lab2](./lab2.md) now. 



