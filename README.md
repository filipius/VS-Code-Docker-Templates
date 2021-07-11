# VS-Code-Docker-Templates
The Visual Studio Code Docker Templates that I use, including for the following technologies:
- LaTeX
- Java
- Python
- Maven
- WildFly
- PostgreSQL
- Kafka (by means of a mount)

Some of these templates use directories that map to my home directory structure, you may have to adapt them to your own case.

For these examples to work you need to put them in a directory called .devcontainer in the root directory that you open with VSCode. VSCode will then ask if you want to reopen inside the container. For example:

```
root
 |
 |- .devcontainer
    |- devcontainer.jso
    |- other files
 |- yourdirectory1
    |- yourfile1
    |- yourfile2
 |- yourdirectory2
    |- yourfile3
 |- yourfile4
 |- yourfile5
```