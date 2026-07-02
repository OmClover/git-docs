1) Find the file by name
->  find . -name "filename.txt"
    . tells to start from current directory
    / can be used to search in entire machine along with sudo to avoid permission denied errors
    *file* can be used if you don't know whole name
    -iname can be used if not sure about case of filename
2) Find the file by type
->  find . -type f -name "*.sh"
    f - file
    d - directory
    l - Symbolic link (shortcut)
    b - block device
    c - character device
    p - named pipe
    s - network communication
3) Find biggest file by size
->  sudo find . -type f -exec du -h {} + 2>dev/null| sort -rh | head -n 1
4) How to remove package?
->  sudo apt remove package_name
    sudo purge package_name (deleted everything like config and custom settings)
5) Find running process
->  ps aux  a-all users  u-user oriented format  x-background/daemon services
    top 
6) Kill the process
->  pkill -9 process_ID
    9 for kill forcefully
    15 for kill gracefully
7) Find location of Software
->  which - gives just a path
    whereis - finds binary executable, manual, source code
    dpkg - low level 'query, finds everything owned by the package
    eg. which python3
8) Install JDK 17+
->  sudo apt install default-jdk
9) Set java home variable
->  check java installation /usr/lib/jvm
    we have to add home variable in /.bashrc
    add following to .bashrc
        export JAVA_HOME="/usr/lib/jvm/java-25-openjdk-amd64"
        export PATH="$JAVA_HOME/bin:$PATH"
    Run command  source ~/.bashrc  to update 
10) Log file location and reading log file
->  location => var/log/
    cat syslog | sort -r | grep "error" | tail 
    cat syslog | sort -r | grep "error" | head


