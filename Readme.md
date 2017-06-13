To understand the steps to convert source code to binary format.

we can use the clang complier's options for each stage and see their output.

Any program will go through the below phases:

1)Preprocessing.
    % clang -E hello.c
2)Compiling.
    % clang -S hello.c
3)Assembling.
    % clang -c hello.c
4)Linking.
    % clang -o hello hello.c


After the final step, we get a file called a.out by default. But we can change the output filename using -o option(clang -o hello hello.c). This will create a binary called hello rather than cryptic a.out(which is short for assembly output.

Now comes the fun part. if you ever try to open a binary file or executable and see garbage characters/scrambled characters rather than o's and 1's, you are not alone.

The reason behind those cryptic characters is any programs that we use (cat, notepad, more) will open the file containing 0's and 1's and convert them to some encoding that they support by default. Hence, we will not be able to see the actual 0's and 1's.

In order to see the actual binary code, we can use tools like "xxd" which is available in most of the linux/mac distro's

    i.e % xxd -b <binary file name>   (ex. % xxd -b a.out)
