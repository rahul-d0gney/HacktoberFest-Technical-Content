# Introduction

In this tutorial, we are going to implement our third Desktop Application using Python and Python’s framework Tkinter. Tkinter provides some tools to implement the Desktop Application. Desktop Application is that which runs on the local machine only, it can't be on the server. So, only the administrator of the computer can use this application.

So we're going to implement the arrangement system desktop application using python. Arrangement System is that application which arranges all the files in a particular folder. We can easily understand using an example. So, for example: If we have a folder and in that folder, there are thousands of files of different types. Files may be Video File, Audio File, Java File, Python File, HTML File, Software File, etc. So, our project takes the path of that folder in an input box. After taking the path, we need to simply click on the Arrange button. After clicking on the arrange button, our model separates all the files in a separate folder. Our project creates all types of folder for all types of files which are available in the folder. And move different types of files in his folder. Like all Audio Files moved into the Audio Files folder, all Video Files moved into the Video Files folder, all Python Files moved into the Python Files folder, etc.


# Let’s start:-

To implement this Desktop Application, first of all you need to install the Python and install the Python’s library Tkinter using the PIP command. Simply write “pip install tkinter”.

First of all import all the required libraries like tkinter, shutil, os, etc. Then set the title of the application using the title() method and also set the height and width of the application using the geometry() method.Then create a frame. On which, we keep the tools like button textbox etc. We use a PhotoImage() method to change the background image of our application. Then we initialize a variable of string type to store the path.


Then create a function to arrange the files. in this function firstly we create a dictionary which stores the key value pairs of extension type and extensions. And initialize one more function  which appends all the files which contain the passed extension and it takes extension type and extension name. Like we passed a .mp4 extension and extension name, so it appended all files of that location in the list and returned the list then moved into the particular folder after creating. And one more condition is that if the folder already exists, it handles the conditions using the else block. It simply moved the file in the folder without creating or deleting the folder. And after arranging all the files, it shows the message like your files have been arranged and if you give the wrong path then it’ll give a warning like you have entered an incorrect path. Then I created one more function for exit from the application. Just simply click on the Exit button, it will exit after saying thank you.


These all are tools which will show on the frame of the Desktop Application. These tools are Label for heading, Entry for taking path in textbox, Button for Arrange and Exit, etc.



# Working
You can see in the below image that all types of files are present in the folder “Arrange”.





We simply copy the path of the folder like “D:\Arrange” and paste into the application as you can see in the image below.




Then simply click on the “Arrange” button and you get a message like “Your files have been arranged”. 




Now you can see in the below image that all files have moved into the particular folder.
