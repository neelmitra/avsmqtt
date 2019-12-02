![alt text](../images/aws_logo.png)

# Lab 2 : Enable Alexa on the NxP MCU kit

In this lab, you will learn how to configure the NxP microcontroller kit to connect to Alexa Voice service and AWS IoT Core. You will start to use Alexa voice commands on the kit. 

## <span style="color:orange"> You will continue to build step 1a of this architecture :</span>
![alt text](../images/arch-1a.png)

## A.  Configure the NxP kit with Alexa
![alt text](../images/nxp-kit.png)

## <span style="color:orange"> You need to establish serial connection to the device : </span>

1. Please connect both the USB ports to the adapter provided, and connect the adapter to the laptop. 
    ![alt text](../images/laptop.jpg) 


2. Connect to the hardware kit using the below instructions - 
    -   Mac -  [screen](./serial.md)
    -   Windows - [putty](./serial.md)
    -   Linux -  [minicom](./serial.md)


2. Once you are connected to device, using the respective terminal software , please run the below commands , one by one, in the SHELL : 

    <span style="color:green">Please enter the commands similar to the screenshot below - </span>

    ![alt text](../images/serial.png) 

    Copy the commands from here : 

    ```
    set_avs_client_id "copy Client id from config.json"

    set_avs_product_id "copy Alexa Product ID from config.json"

    set_aws_endpoint_url "copy IoT core URL from cloudformation outputs in lab1 "

    set_aws_account_id "copy AWS Account ID provided to you"

    set_cbl_mode 1

    setup Condensate "!Dev1ces+Are+Com1ng!"

    ```

    This will restart your device , please connect back to the device using seral command and run the below. 

    ```
      enable_usb_log
      logs
    ```

    <span style="color:orange">If the session exits for some reason anywhere, please connect to the serial terminal again.</span>

    You will get the User code and the URL from the console : 

    ![alt text](../images/reg1.png) 

4.  Copy the user code from the logs and navigate to [amazon.code](https://amazon.com/us/code) on your browser to authenticate - 

    - Login with the same email , if prompted, that you used for the Alexa developers console prior in Lab 1
    - Paste the user code and submit. *Registration successful* should appear on the web page 

    ![alt text](../images/lwa.png) 

6. Check back on the serial terminal - 
    - Device will periodically check for a token, may take up to 60 seconds
    - After that it will register and be ready to use.
    - The log will show if any errors. 

    ![alt text](../images/reg2.png) 



    <span style="color:orange"> If connection and auth is successful , the board will only have the power green led on.
    
    ![alt text](../images/board1.png) 

    <span style="color:orange">If the board is muted there will be a red led on, along with the green power led. 
    </span>

    ![alt text](../images/board1.png) 

## <span style="color:green"> Try Alexa, time in las vegas </span>

    *And get to know about the fantastic weather in vegas.*

## B.  Navigate to AWS IoT console 

Please login to the [AWS IoT Console](https://console.aws.amazon.com/iot/) and select *Manage* (on the left pane) -> Things. 

1. Check if you can see the Thing created with the serial # of your NxP kit (on the right pane). 
2. Click on *Monitor* (left pane) and check on the graphs (in the right pane) for successfull Connections and Messages.  

To learn more about AVS Integration for AWS IoT, please click [here](https://developer.amazon.com/docs/alexa-voice-service/avs-for-aws-iot-overview.html).


## <span style="color:green"> Try Alexa, time in las vegas </span> once again on the device 

And check in the IoT *Test* console  , you will see encrypted voice event messages appearing. 

Congratulations! You now have access to the Alexa Voice Service APIs from your hardware and able to subscribe the messages from the hardware using AWS IoT console. 

### See you in [lab3](./lab3.md). 











