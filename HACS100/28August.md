# HACS 100
### Wed. August 28th, 2019
---

## First day of Unix

__Components:__
- made up of many simple tools (_modular_)
- shared file system

---

### Levels of UNIX
* kernel
    - interacts w/ hardware
* libraries/system calls
    - programs called by the shell
* shell
    - many shells available
    - mainly differ in style only

### Shell Command Structure
* `% [command name] [option(s)] [argument(s)]`
* all case-sensitive

### Useful commands
* `% ssh -l [username] [address]`: Creates a secure shell to the address and logs in using the username
    - ex. `% ssh -l reid terpconnect.umd.edu`
* `exit` OR `logout`: Closes the ssh connection
* `% finger [name]`: Info about a user
    - `-m` option matches only on username, not first/last name
* `% man [command name]`: __Manual__ for a command
    - `-k` argument searches command manuals by keyword rather than command name
        * Follow the keyword by ` | more` to limit the number of manuals displayed at once