# Linux

	tar -czvf name-of-archive.tar.gz /path/to/directory-or-file

	grep -r "some text" .

    find . -name <pattern>

## Open ports

    netstat -nat | grep LISTEN
    netstat -an | grep PORTNUMBER | grep -i listencat /etc/*-releasecat /etc/*-release

## Linux version

    cat /etc/*-release

## CPU info

    cat /proc/cpuinfo

## Write a loop:

    for ((start=1; start <= 5; start++));
        do
            wget fortunes-ui-wes.south.fe.pivotal.io
            rm index.html
            sleep 3
        done

## Stress CPU Load

    sudo apt-get install stress
    stress -cpu 2 -timeout 60

## Linux Programs

### Editor - Visual Studio

    https://code.visualstudio.com/download

### Screencast, Screenshot, Screen Recording - Kazam

    sudo apt-get install kazam

### Photo editing - Gimp

###