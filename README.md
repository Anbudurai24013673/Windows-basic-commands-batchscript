# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"


## COMMAND AND OUTPUT

```
mkdir my-folder


```

<img width="1240" height="107" alt="image" src="https://github.com/user-attachments/assets/48d0d5fe-c22a-4f11-b73f-9daa6ad649ca" />



Remove the directory "my-folder"



## COMMAND AND OUTPUT

```
rmdir my-folder


```

<img width="1245" height="100" alt="image" src="https://github.com/user-attachments/assets/45001fce-5e84-41c1-b87e-fe9c5844568b" />




Create the file Rose.txt



## COMMAND AND OUTPUT


```
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z

dir Rose.txt

```

<img width="1218" height="417" alt="image" src="https://github.com/user-attachments/assets/5528a6d0-be18-4c25-8aa6-954ca5833d85" />




Create the file hello.txt using echo and redirection



## COMMAND AND OUTPUT


```
echo “hello world” > hello.txt
type hello.txt


```

<img width="1223" height="88" alt="image" src="https://github.com/user-attachments/assets/3e4d6d9f-a32d-4ccb-8dbd-bac639a58c8b" />





Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT




```
copy hello.txt hello1.txt

```

<img width="1241" height="135" alt="image" src="https://github.com/user-attachments/assets/19660e8e-88bc-4199-b7c6-d43af40b0353" />






Remove the file hello1.txt

## COMMAND AND OUTPUT
```

del hello1.txt



```

<img width="1242" height="98" alt="image" src="https://github.com/user-attachments/assets/3d4152a5-e4d8-41f8-8e0d-fc13905b16bb" />




List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT

```
dir hello1.txt
```


<img width="1217" height="196" alt="image" src="https://github.com/user-attachments/assets/34a45385-1e93-4093-80a1-72d59c704d26" />






List out all the associated file extensions 

## COMMAND AND OUTPUT
```
assoc | more

```
<img width="646" height="733" alt="image" src="https://github.com/user-attachments/assets/0c4d5516-67c0-4d02-a547-e8595046887d" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT


```
fc hello.txt Rose.txt


```

<img width="1241" height="207" alt="image" src="https://github.com/user-attachments/assets/9b1411bf-348b-4c73-953d-c43ee9e9fdfc" />



## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```

@echo off
set name=John
echo Hello, %name%!
pause




```



## OUTPUT

<img width="1101" height="86" alt="image" src="https://github.com/user-attachments/assets/e073a9ef-165e-4fcd-9267-6f25e6ef764d" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```

@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause



```


## OUTPUT


<img width="1111" height="350" alt="image" src="https://github.com/user-attachments/assets/9d4734db-5c08-4519-b5d8-0c7619b9bfea" />


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```

@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause




```


## OUTPUT

<img width="1137" height="202" alt="image" src="https://github.com/user-attachments/assets/119f31b1-77cf-4e0f-b344-20d1c25e52aa" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause




```

## OUTPUT

<img width="1198" height="207" alt="image" src="https://github.com/user-attachments/assets/3267fc64-d4d5-4a71-89e5-88742ecbec0b" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause




```


## OUTPUT

<img width="1102" height="521" alt="image" src="https://github.com/user-attachments/assets/2e242370-1490-4192-95ef-b72e03329b8c" />


# RESULT:
The commands/batch files are executed successfully.

