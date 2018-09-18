# ping

a ping command line from unp, this code just let me pratice the related gcc command.

__Notice: this code only build on macos__

## build share library

    gcc lib/*.c -shared -fPIC -o libunp.so -w

## build static library

    cd lib/
    gcc -c *.c -w
    cd -
    ar rv libunp2.a lib/*.o

## build executable file with share library

    gcc *.c -Ilib/  -o ping  -L. -lunp -D__APPLE_USE_RFC_3542 -w

## build executable file with static library

    gcc *.c -Ilib/  -o ping  -L. -lunp2 -D__APPLE_USE_RFC_3542 -w


## run

    # the raw socket need root permission
    sudo ./ping

## check dependencies of executable file

    # use share library
    otool -L ping
    ping:
            libunp.so (compatibility version 0.0.0, current version 0.0.0)
            /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1252.50.4)


    # use static library
    otool -L ping
    ping:
            /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1252.50.4)
    
