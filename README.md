# Scan Server

Scan server is a Free to use alternative to many expensive solutions out there that allow scanning documents from Web applications.

## Project Structure

There are two projects:
1. ScanServer: Compiles into a .exe that can be run a standalone app or as a service
2. ScanServerInstaller: Create an MSI to make easier to download and install as Windows Service (Runs by default on http://localhost:5000).

## How to use

Just run/install the app.
List the devices on: http://localhost:5000/api/scanners


## Getting started

To build this project:

```ps
cd .\ScanServer
rm -r .\bin\
dotnet clean
dotnet publish ScanServer.csproj -c Release
cd ..\ScanServerInstaller
rm -r .\bin\
dotnet clean
dotnet build -c Release
```


## Uninstall:

To uninstall start a command line as administrator and run:

```cmd
sc stop ScanServer
sc delete ScanServer
```

Then delete the install folder.

# Naps2

A huge thank you to @cyanfish and it's [NAPS2 SDK Project](https://github.com/cyanfish/naps2/) without whom/which building this would have taken a lot of time.
If you want to donate, please donate to him using this [link](https://www.naps2.com/donate?src=scan-server)

# TODO
Find a way to change the default port in the service either:
1. by configuring the service in the installer
2. Building the app with another default port while allowing --urls to work.