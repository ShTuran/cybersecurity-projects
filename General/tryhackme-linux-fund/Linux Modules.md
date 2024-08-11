# Is there a difference between egrep and fgrep? (Yea/Nay)

'Yea'. `egrep` is for extended, complex patterns but  `fgrep` is for fixed string

You can also use `grep -E` for egrep,

`grep -F` for fgrep

# Which flag do you use to list out all the lines NOT containing the 'PATTERN'?

'-v' as tutorial mentioned - "This flag prints all the lines that are NOT containing the pattern"

# Download the above given file and answer the following questions.

✅

# What user did you find in that file?

`cat grep.txt | grep -i "user"`

`cat`  will output the context of 'grep.txt'

`grep` will select the specified word

'-i'  means that ignore case sensitivity

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/d4c578ca-60b8-474b-943c-8920ce769470)

# What is the password of that user?

`cat grep.txt | grep -i "password"`

`cat`  will output the context of 'grep.txt'

`grep` will select the specified word

'-i'  means that ignore case sensitivity


# Can you find the comment that user just left?

`cat grep.txt | grep -i "comment"`

`cat`  will output the context of 'grep.txt'

`grep` will select the specified word

'-i'  means that ignore case sensitivity


# Run tr --help command and tell how will you select any digit character in the string?

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/20344590-2b39-43f7-aadb-3b05863bd69f)

`:digit:`

# What sequence is equivalent to [a-zA-Z] set?

`:alpha:` as mentioned above use tr --help command to get the necessary thing.

# What sequence is equivalent to selecting hexadecimal characters?

`:xdigit:` as mentioned above use tr --help command to get the necessary thing.

# Download the above given file, and use awk command  to print the following output:

`ippsec:34024
john:50024
thecybermentor:25923
liveoverflow:45345
nahamsec:12365
stok:1234`

- We had 4 field, so the text wanted us to output 1st and 4th field ->  `print{$1,$4}`


    BEGIN: This is a special pattern in awk that is executed before processing any input lines. It allows you to set up variables, perform initializations, or define actions that should happen before the main processing begins.

    FS: Stands for "Field Separator." It is used to specify the character or regular expression that separates fields in the input. By default, awk assumes fields are separated by whitespace (spaces or tabs). In this case, FS=" " sets the field separator to a single space, meaning awk will treat consecutive spaces as a single delimiter for fields.

    OFS: Stands for "Output Field Separator." This variable determines how fields are separated in the output. When awk prints its output, it uses OFS to join the fields together. By default, OFS is a space. Here, OFS=":" sets the output field separator to a colon :. So, when awk prints any output, it will separate fields with colons instead of spaces.

As a result, our command will be:

`awk 'BEGIN{FS=" "; OFS=":"}  {print $1,$4}' awk.txt`




# How will you make the output as following (there can be multiple; answer it using the above specified variables in BEGIN pattern):

`ippsec, john, thecybermentor, liveoverflow, nahamsec, stok`

    BEGIN{ORS=","}:
        BEGIN is a special pattern in awk that is executed before processing any input lines.
        ORS stands for "Output Record Separator." It defines the character or string to be printed between records (lines) of output.
        In this case, ORS="," sets the Output Record Separator to a comma ,. This means that when awk prints the output, it will separate each line with a comma.

    {print $1}:
        This is the main block of the awk command, executed for each line of the input file.
        {} denotes the action block.
        print $1 instructs awk to print the first field ($1) of each input line.
        $1 refers to the first field of the current input line.

    awk.txt:
        This is the input file that awk processes.


As a result, our command will be:      

'awk 'BEGIN{ORS=","} {print $1}' awk.txt'

![image](https://github.com/ShTuran/tryhackme-linux.fundamentals/assets/111232034/a312309a-ab72-48d1-ad7c-fa68a900231c)


# How would you substitute every 3rd occurrence of the word 'hack' to 'back' on every line inside the file file.txt?

`sed 's/hack/back/3g' file.txt`


# How will you do the same operation only on 3rd and 4th line in file.txt?

`sed '3,4 s/hack/back/3g' file.txt`

# Download the given file, and try formatting the trailing spaces in sed1.txt with a colon(:).

'sed 's/ */:/g' sed1.txt' 

# View the  sed2 file in the directory. Try putting all alphabetical values together, to get the answer for this question.

`sed 's/[[:digit:]]//g' file.txt`

'CONGRATULATIONS YOU MADE IT THROUGH THIS SMALL LITTLE CHALLENGE'

# What pattern did you use to reach that answer string?

‘s/[[:digit:]]//g’

# Alternatively, you can use tr to remove all the digits, and then pipe the output in sed to remove trailing whitespaces.

`cat sed2.txt | tr '[:digit:]' ' ' | sed 's/  *//g'

[Update] Another good way suggested by a room do-er. You can simply use tr -d command to delete all the digits from the file.

cat sed2.txt | tr -d '[:digit:]' `

# What did she sed?(In double quotes)

"That's What"

# You're working in a team and your team leader sent you a list of files that needs to be created ASAP within current directory so that he can fake the synopsis report (that needs to be submitted within a minute or 2) to the invigilator and change the permissions to read-only to only you(Numberic representation). You can find the files list in the "one" folder.

Use the following flags in ASCII order:

    Verbose
    Take argument as "files"

`cat file | xargs -I files -t sh -c “touch files; chmod 400 files”`

# Your friend trying to run multiple commands in one line, and wanting to create a short version of rockyou.txt, messed up by creating files instead of redirecting the output into "shortrockyou". Now he messed up his home directory by creating a ton of files. He deleted rockyou wordlist in that one liner and can't seem to download it and do all that long process again.

He now seeks help from you, to create the wordlist and remove those extra files in his directory. You being a pro in linux, show him how it's done in one liner way.

Use the following flags in ASCII order:

    Take argument as "word"
    Verbose
    Max number of arguments should be 1 in for each file

You can find the files for this task in two folder.

'ls | xargs -I word -n 1 -t sh -c ‘echo word >> shortrockyou; rm word’'

# Which flag to use to specify max number of arguments in one line.

`-n`

# How will you escape command line flags to positional arguments?

`--`

# Download the file given for this task, find the uniq items after sorting the file. What is the 2271st word in the output.

`lollol`

`sort test.test | sed -n 2271p`

# What was the index of term 'michele'

`2550`

# Which flag allows you to limit the download/upload rate of a file?

`--limit-rate`

# How will you curl the webpage of https://tryhackme.com/ specifying user-agent as 'juzztesting'

`curl -A 'juzztesting' https://tryhackme.com`

# Can curl perform upload operations?(Yea/Nah)

`Yea`

# How will you enable time logging at every new activity that this tool initiates?

`-N` -> Enables timestamping 

# What command will you use to download https://xyz.com/mypackage.zip using wget, appending logs to an existing file named "package-logs.txt"

-a package-logs.txt: This option is used to specify a log file where wget will append its messages. In this case, package-logs.txt is the name of the log file. If the file doesn't exist, wget will create it. If it does exist, wget will append new messages to it without overwriting the existing content.

https://xyz.com/mypackage.zip: This is the URL of the file you want to download. In this example, it's a ZIP file (mypackage.zip) located at https://xyz.com/.

As a result, our command will be:      

`wget -a package-logs.txt https://xyz.com/mypackage.zip `

# Write the command to read URLs from "file.txt" and limit the download speed to 1mbps.

     -i file.txt: This option tells wget to read the list of URLs to download from the specified file (file.txt). In file.txt, you would typically have a list of URLs, each on a separate line. wget will then proceed to download each URL in the list.

    --limit-rate=1m: This option sets the download speed limit. In this case, 1m specifies a limit of 1 megabyte per second. You can adjust this value to limit the download speed to a specific rate.

As a result, our command will be:      

`wget -i file.txt --limit-rate=1m`


# How will you seek at 10th byte(in hex) in file.txt and display only 50 bytes?

`xxd -s 0xa -l 50 -b file.txt`

# How to display a n bytes of hexdump in 3 columns with a group of 3 octets per row from file.txt? (Use flags alphabetically)

`xxd -c 9 -g 3 file.txt`

# Which has more precedence over the other -c flag or -g flag?

'-c'

# Download the file and find the value of flag.

`cat flag.txt | xxd -r -p ` will give the flag

# It's safe to run systemctl command and experiment on your main linux system neither following a proper guide or having any prior knowledge? (Right/Wrong)

`wrong`

# How will you import a given PGP private key. (Suppose the name of the file is key.gpg)

`gpg --import key.gpg`

# How will you list all port activity if netstat is not available on a machine? (Full Name)

`Socket Statistics`

# What command can be used to fix a broken/irregular/weird acting terminal shell?

`reset`
