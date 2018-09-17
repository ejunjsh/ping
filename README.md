# ping
a ping command line from unp, this code just let me pratice the related gcc command.

__Notice: this code only build on macos__

## build share library

    gcc lib/*.c -shared -fPIC -o libunp.so

## build executable file

    gcc *.c -Ilib/  -o ping  -lpthread -D__APPLE_USE_RFC_2292 -L. -lunp

## set owner to root

    sudo chown root:wheel ./ping

## set +s permission 

    sudo chmod u+s ./ping
