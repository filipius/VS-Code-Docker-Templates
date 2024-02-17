# VS-Code-Docker-Templates
One of the greatest features of Visual Studio Code is the ability to connect to a Docker container and run the entire development environment attached to that container. Ultimately, one may have a very minimal installation on his/her computer apart from Docker Desktop and VS Code itself and (automatically) install and (manually) delete images and containers whenever necessary. This option enables having a slim minimalistic computer while offering the same development environment for teams and the same person across multiple computers.

This option has some shortcomings:
1. One must set up each environment with a set of folders and text files, which might range from simple to complex if one needs an application server, a command line, and a database, for example.
2. The default shell is not properly configured.

Hence, in this repository, I collected some environments, for different programming languages, based on one or more Docker containers. The Visual Studio Code Docker Templates I use, include the following technologies:
- LaTeX
- Java
- Python
- Maven
- WildFly
- PostgreSQL
- Kafka (using a mount)
- some of the previous options together

To make these templates work, you need to copy the .devcontainer to your working folder, as follows:

```
working folder
 |
 |- .devcontainer
    |- devcontainer.json
    |- other files
 |- yourfile1
 |- yourfile2
 |- yourdirectory1
    |- yourfile11
    |- yourfile12
...
```

Then, you should open the working folder with VS Code (Menu File->Open Folder). You need to have the Remote Development extension installed, but VS Code will usually offer to install it if it is not yet there. Then accept the option to Reopen the folder in a container in the notification that VS Code will show or explicitly search for that option on the lower left corner icon of the Remote Delopment extension.

