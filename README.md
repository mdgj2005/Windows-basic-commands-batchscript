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
## Create a directory named "my-folder"

 __COMMAND AND OUTPUT__
 ![1 mkdir myfolder](https://github.com/user-attachments/assets/8cdb9cc8-8784-4e3b-a39d-07f9099549e8)


## Remove the directory "my-folder"

**COMMAND AND OUTPUT**
![2 rmdir myfolder](https://github.com/user-attachments/assets/13ef1722-e569-4386-a9c8-7f1e7ddd2eb3)


## Create the file Rose.txt

**COMMAND AND OUTPUT**
![3 rose](https://github.com/user-attachments/assets/6f096331-d44f-4926-97e3-2bdff394fbc0)


## Create the file hello.txt using echo and redirection

 __COMMAND AND OUTPUT__
![4 hello](https://github.com/user-attachments/assets/97fdbd7c-e582-4ac5-b8cb-1b7a637b92ad)


## Copy the file hello.txt into the file hello1.txt

__COMMAND AND OUTPUT__
![5 copy hello](https://github.com/user-attachments/assets/f3fc5996-7fbe-4442-ace7-815ecc430f50)


## Remove the file hello1.txt

 __COMMAND AND OUTPUT__
![6 del hello1](https://github.com/user-attachments/assets/a00815b1-5667-4bed-b9ac-77288975fcc8)


## List out the file hello1.txt in the current directory

 __COMMAND AND OUTPUT__
![7 dir hello1](https://github.com/user-attachments/assets/06851261-be55-4923-b874-8b1ac4dcd47f)


## List out all the associated file extensions 

__COMMAND AND OUTPUT__
![8 assoc1](https://github.com/user-attachments/assets/ecf0977f-3f6a-4004-8ce8-2c1fd3e854d0)
![9 assoc2](https://github.com/user-attachments/assets/5913b7a7-247f-42de-89ac-dac7b57d7813)
![10 assoc3](https://github.com/user-attachments/assets/0de7155c-f17d-4ab9-92ec-e75059c70dfa)
![11 assoc4](https://github.com/user-attachments/assets/3e6fcd33-83a0-41a0-8ab0-a2b02d4b11cf)
![12 assoc5](https://github.com/user-attachments/assets/3a22fd7a-e7cf-401e-a4b8-31677dab5988)
![13 assoc6](https://github.com/user-attachments/assets/f23f8824-6c34-441a-90ca-4bd3e783a3b6)
![14 assoc7](https://github.com/user-attachments/assets/5ca9d01c-51fc-48e9-b968-ca38670c9613)
![15 assoc8](https://github.com/user-attachments/assets/bee8ed1e-dc53-4f55-9ef5-532fb2bb0a34)
![16 assoc9](https://github.com/user-attachments/assets/f0d46be7-f413-4e27-bc3e-40a90d693856)
![17 assoc10](https://github.com/user-attachments/assets/889545e1-bc3f-44ad-9883-b826183b5f6f)
![18 assoc11](https://github.com/user-attachments/assets/3b5cfa0a-2633-48d4-af99-eab1ff8dc11e)

## Compare the file hello.txt and rose.txt

 __COMMAND AND OUTPUT__
![19 fc hello Rose](https://github.com/user-attachments/assets/9a58bdca-bfa8-43a1-880a-11a2d203f1be)


## Exercise 2: Advanced Batch Scripting
__1__.Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

### BATCH PROGRAM

``` batch
@echo off
set name=John
echo Hello, %name%
pause
```
### OUTPUT
![20 hello_name](https://github.com/user-attachments/assets/24e108bb-1ce7-4b17-99d0-931ddd0c4dbf)


__2__.Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

### BATCH PROGRAM
``` batch
@echo off
:loop
set /p num=Enter a number: 
set /a rem=%num% %% 2

if %rem%==0 (
    echo %num% is Even
) else (
    echo %num% is Odd
)

:ask
set /p ans=Do you want to check another number? (Y/N): 
if /I "%ans%"=="Y" goto loop
if /I "%ans%"=="N" goto end
echo Invalid input. Please enter Y or N.
goto ask

:end
echo Thank you!
pause
```

### OUTPUT
![21 check_odd](https://github.com/user-attachments/assets/127eb99a-b4e4-4e01-b5a1-7801e9c5a12e)


__3__.Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

### BATCH PROGRAM

``` batch
@echo off
for /L %%i in (1,1,5) do (
    echo Number: %%i
)
pause
```

### OUTPUT
![22 loop_display](https://github.com/user-attachments/assets/5b43292a-0d1b-4c33-af2b-7d177df8cf0c)


__4__.Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

__Instructions:__
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

### BATCH PROGRAM

``` batch
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
```

### OUTPUT
![23 check_file](https://github.com/user-attachments/assets/1c6d824b-12e1-40cd-b675-87ea2dad2c0a)


__5__.Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

### BATCH PROGRAM

``` batch
@echo off
:menu
cls
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option (1-3): 

if "%choice%"=="1" goto hello
if "%choice%"=="2" goto create
if "%choice%"=="3" goto exit
echo Invalid choice.
pause
goto menu

:hello
echo Hello, World!
pause
goto menu

:create
echo This is a new file > newfile.txt
echo File newfile.txt created.
pause
goto menu

:exit
echo Goodbye!
pause
exit
```

### OUTPUT
![24 newfile1](https://github.com/user-attachments/assets/2802b121-a4dd-4786-8997-aa1cdd46e94c)
![25 newfile2](https://github.com/user-attachments/assets/d1a9db51-bdac-465b-acf2-07c92566bba2)
![26 newfile3](https://github.com/user-attachments/assets/5a2e18e8-b080-4950-871d-6cc0200b4d89)


# RESULT:
The commands/batch files are executed successfully.

