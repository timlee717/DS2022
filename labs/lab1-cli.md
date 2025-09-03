# Case Study 1 part 2: Visual Studio (Cursor) and Linux Command Line. 

## Downloading and install Cursor. 
Cursor is a great integrated development environment built on top of visual studio code.  Cursor has LLM integration built-in so that you can chat with and update your code. We strongly encourage you to do this. This tool help you build and debug.  
Visit <a href="https://cursor.com"> https://cursor.com </a> and download the Cursor IDE for your specific system. 

### Connecting to the University of Virginia High Performance Computing Cluster. 
Connect to the cluster using ssh. Once you launch cursor and select your preferences; click new ssh table to begin the process of connecting to the cluster.  
![Select ssh](../images/labs/lab1/connecttossh.png)

Now type your_computing_id@login.hpc.virginia.edu into the command window and then type in your host when prompted. 
![host info](../images/labs/lab1/loginhostinfo.png)

Finally click open folder and select the option /home/your_computing_id/

![OpenFolder](../images/labs/lab1/Openfolder.png)

You development environment is now connected to the cluster. 


# Case Study 1 Part 2: Visual Studio (Cursor) and Linux Command Line

## Step 1: Download and Install Cursor
Cursor is a special version of Visual Studio Code that has AI (LLM) features built in.  
This means you can chat with it, ask questions, and even get help fixing your code.  
It’s like having a coding assistant built right into your editor.  

Go to [https://cursor.com](https://cursor.com)  
Download the installer for your computer (Mac, Windows, or Linux)  
Run the installer to set up Cursor on your system  

---

## Step 2: Open Cursor and Set Up SSH
We will use Cursor to connect directly to the **University of Virginia High Performance Computing (HPC) Cluster**.

1. Launch **Cursor**.  
2. Go to your preferences (the settings menu).  
3. Click **Connect Via SSH ** to begin creating a connection.  

![Select SSH](/DS2022/images/labs/lab1/connecttossh.png)

---

## Step 3: Log In to the HPC Cluster
1. In the SSH connection box, type:  

your_computing_id@login.hpc.virginia.edu

Replace `your_computing_id` with your actual UVA computing ID.  

![Host Info](images/labs/lab1/loginhostinfo.png)

2. When prompted, type in your **password**.  

## Step 4: Open Your Home Folder
1. After you log in, click **Open Folder**.  
2. Choose this option:  

/home/your_computing_id/


![Open Folder](images/labs/lab1/Openfolder.png)

---
That’s it! Your Cursor editor is now connected to the UVA HPC cluster.  
From here, you can write code locally in Cursor and run it on the cluster without leaving the editor. 



## Getting Oriented to your Home Directory
Follow all the steps below for practice with the command line. At the bottom are instructions for commands you should write for each prompt, saved to a text file you create using the command line. Paste the contents of that file to the Lab assignment page for grading.

1. Change directories to your home directory by issuing the `cd ~` command. `cd` is short for "change directory". This is a shortcut to your home directory.

```
cd ~
```

2. Learn the location of your home directory by issuing the `pwd` command. `pwd` is short for "present working directory". 

```
pwd
```

3. List all the contents in your home directory by using the `ls` command.

```
ls
```

Next try listing the contents in a more detailed view

```
ls -l
```

Next try listing all contents, including hidden files and directories

```
ls -al
```

Hidden files and directories start with a `.` such as `.ssh` or `.bashrc`.

Note that the `-al` flags (or options) do not have to be in any particular order. So you could also issue this command:

```
ls -la
```

5. Create two empty files by using the `touch` command

```
touch file1
touch file2
```

List the directory contents again to see the files listed.

Next, try creating two more files within the same command:

```
touch file3 file4
```

6. Add text contents to a file. You can use `echo` to pass some data into a file like this:

```
echo "Hi there everybody, my name is <YOUR NAME>" > file1
```

This command uses a "redirect" to take the `echo` command and push it into `file1`.
You could actually just `echo` out anything you want, at any time, but it only prints
to the screen and isn't recorded anywhere. Try it for yourself:

```
echo "Today is Friday"
echo "A man a plan a canal Panama"
```

7. View the contents of your file using `cat`. `cat` is short for concatenate, since it can
easily join files together, but it's often used simply for reading out the contents of a single
file.

```
cat file1
```

Should result in you seeing the command you echoed into it earlier. You can `cat` out other
files as well:

```
cat .bashrc
```

```
cat .bash_history
```

8. Whenever you are in a directory you can read, edit, or list a file easily using its short
name, like this:

```
cat .bashrc
```

But every file or folder can be referred to by its full path within the file structure.
For example, your home directory in the Google Shell might look like `/home/mst3k`, so you can also cat
things using their "full path":

```
cat /home/mst3k/.bashrc
cat /home/mst3k/file1
```

This is extremely useful since it means *you do not have to change into a directory just to work with its contents*.

9. Move Up and Down Directories

Try changing to the "parent" directory with the `cd` command and the parent directory shortcut `..`:

```
cd ..
```

From your home directory you are now in the `/home` directory. Verify that by issuing the `pwd` command.

You can change back to your home directory in at least three ways. Assuming the home directory is
named `mst3k` and you are in `/home` then:

```
cd mst3k
cd /home/mst3k
cd ~
```

## Working with Folders (Directories)

1. Create a subdirectory

From within your home directory create a new directory using the `mkdir` (make directory) command:

```
mkdir mynewdir
```

List the contents of your home directory and you should see the new subdirectory appear:

```
ls -al
```

2. Can you already guess the full path of the new subdirectory you created? If not, `cd` into
it and then issue the `pwd` command to find out.

3. What if you want to rename a directory? Use the `mv` command:

```
mv mynewdir another-newdir
```

4. To delete a directory, use the `rm` command with the `-R` (Recursive) option. Recursive
means you want to delete the directory AND anything within it.

```
rm -R another-newdir
```

## Working with Text Files

1. A simple, built-in text editor is called `nano`. To open `nano` with an empty, blank document
simply invoke the `nano` program:

```
nano
```

Within the page you see blank space where you will write contents, and a series of possible
commands at the bottom marked with the `^` character. This stands for the CONTROL key. If you
open a blank document, try writing several lines of text, complete with paragraph breaks and 
punctuation. When you're done, press `^X` to exit. Upper/lower case does not matter.

This will give you the following prompt:

```
Save modified buffer (ANSWERING "No" WILL DESTROY CHANGES) ? 
```

To save your buffer (your open document) just press the `Y` key. This will give you a final prompt:

```
File Name to write : 
```

Here you can name your file anything you want. It will be saved to the directory you were in
when you opened up `nano`.

2. `cat` out the contents of the file you just edited.

3. Now rename the file you just created by using the `mv` command. The syntax is:

```
mv <ORIGINAL-NAME> <NEW-NAME>
```

So if you just created `hello.txt` in `nano` earlier, you could rename it by moving it:

```
mv hello.txt hello
```
You can always move a file to a completely different location by using a full path reference.

```
mv hello.txt /another/directory/hello.txt
```
This moves the `hello.txt` file in your current directory to a new location.


4. Pipe one command into another using the `|` character.

Above you saw how a `cat` command could be redirected into a file. There is also the `|` "pipe"
command when you want to couple the text output of one command and process it using a second (or more)
command. 

Since you know `cat` prints out the contents of a file, let's join it with the `wc` (word count)
command:

```
cat hello | wc
```

This will print out three numbers:

```
  171   812   4522
```
This means the file is 171 lines long, contains 812 words, and is 4522 characters long.

You can always request one of these values at a time by using option flags with the `wc` command. If you would like a line count only, use `-l`:

```
cat hello | wc -l
```
For a word count only, use `-w`

```
cat hello | wc -w
```

5. Copying files or directories. If you have a file or folder you would like to copy, use the `cp`
command like this:

For a file:
```
cp file1 file2
```

For a directory:
```
cp -R dir1 dir2
```

Notice it is a good practice to leave the trailing `/` off of directory names.

## Finding Things

One of the simplest search tools is called `grep` which prints out results based on
"regular expressions" - these are filters, in a way, to help you find things.

1. Let's fetch a large text from a remote source so that we can search through it:

```
curl -s https://gist.githubusercontent.com/StevenClontz/4445774/raw/1722a289b665d940495645a5eaaad4da8e3ad4c7/mobydick.txt > mobydick.txt
```
You should now have a local file named `mobydick.txt`. Let's look at the first few lines of the book by using the `head` command:

```
head mobydick.txt
```
(This version has some gibberish in the front - but that's okay)

Let's search through the book using `grep`, which we will pipe after a `cat` command. `cat` will echo out the book contents into
`grep` which will filter and print ONLY lines where the search term appears.

```
cat mobydick.txt | grep "Captain"
```

2. This prints out a lot of results. What if we wanted to count how many lines the word
"Captain" appears? We can pipe on another command to count lines, like this:

```
cat mobydick.txt | grep "Captain" | wc -l
```

How many lines contain "Captain" in this text?

**Side note:** `grep` is case-sensitive, so what if we ran the same command searching for lower-case "captain"?

```
cat mobydick.txt | grep "captain" | wc -l
```

3. What if we wanted to search across many files for a word? `grep` is still useful here. Issue this command from within your home directory:

```
grep -r "Captain"
```

The output will contain both the file name where the search term appears and the relevant
line itself

```
./mobydick.txt:person, yet for Captain Ahab to have a boat actually 
./mobydick.txt:above all, for Captain Ahab to be supplied with five extra 
./mobydick.txt:about to be narrated, never reached the ears of Captain 
./mobydick.txt:handspikes, my hearties. Captain, by God, look to 
./mobydick.txt:Captain Colnett, a post-captain in the English navy, 
```

4. Finding files by file name. Use the `find` command for this. The syntax is:

```
find . -name "mobydick.txt"
```

This issues the find command, searching the present directory (signified by the `.`)
with the name `"mobydick.txt"`. Note that the filename must be an exact match.

To search across all home directories, for example, you would change the path option

```
find /home -name "filename.txt"
```

5. Finding files matching a pattern

Use the wildcard `*` character at the beginning, middle, or end of a term to extend
matching. For example, if you only knew that `moby` was in the name of the file and
nothing more, this command would work:

```
find . -name '*moby*'
```

Or if you wanted to file all text files by suffix in a directory

```
find . -name '*.txt'
```

6. Wildcard matching

The wildcard `*` is useful in many contexts:

List all files ending with `.pdf`

```
ls -al *.pdf
```

Delete all files containing "zero" in the name:

```
rm -R '*zero*'
```

## File Permissions

1. Touch a file named `permissiontest` and echo some content into it. 

2. Next use `ls -al` to see it listed in your directory.

3. Now change its permissions to `000` like this:

```
chmod 000
```

Try to `cat` the contents of the file. You should get a permission denied message.

4. Now change its permissions so that only you can read and write the file:

```
chmod 600
```

Again, `ls` the directory so you can see the permission bits for the file.

5. Finally, let's grant other members of your group read access, along with the access
we already gave you:

```
chmod 640
```

List the directory contents once more and notice the permission bits for the file.


## Utility Commands

These commands are used a bit less frequently but can help with basic tasks.

### `top`

`top` or `htop` shows you current processes, memory and CPU usage. They allow you
to see the `pid` (process ID) for any process, so that you can monitor it or stop (kill) it.

### `w`

`w` (who) shows you current users of your system. Typically if you are on a laptop
or desktop computer you own, you will be the only user. But large HPC computers may
have hundreds of users logged in concurrently.

### `which`

`which` shows you the path to a specific application. For instance, let's find Python3
on the local system:

```
$ which python3
/usr/bin/python3
```

The binary code for Python3 lives within `/usr/bin` - a very normal place for it to be.

You may want to list the contents of the `/usr/bin` directory to get a sense for all the 
built-in commands within the Linux kernel and `bash` shell.

```
ls -al /usr/bin
```

### `zip` and `tar`

Compressing or decompressing archives like zips or tarballs is not too difficult:

To create a zip bundle, assuming we are in a directory with `file1` and `file2` we want to zip up:


```
zip archive.zip file1 file2
```

This creates a zip file named `archive.zip` containing the two files. To unzip, the command is
quite simple:

```
unzip archive.zip
```

To create a tarball (the common nickname for a tar compressed archive) we often use it in conjunction
with the `gzip` and `gunzip` options to keep the archive as small as possible. Again assuming we have two files in the current directory named `file1` and `file2` we want to put in the bundle:

```
tar -czvf archive.tar.gz file1 file2
```

The `-czvf` options mean: `-c` for CREATE an archive, `-z` for `gzip` the archive,
`-v` for verbose output, and `-f` for write the archive to a file.

To decompress the same archive:

```
tar -xzvf archive.tar.gz
```

The only difference in options is the use of `-x` which means "expand"

NOTE: It's extremely useful to know that in the world of the command line you can always add or remove files from archives without re-creating them! They are editable objects using when using either the `zip` or `tar` commands.

### `history`

Displays your history of commands in `bash`. Often this is limited to 1000 but that can
be changed in your `.bashrc` file.

### `!999`

When viewing your history, notice the line number with each command. To repeat an item in your history, prefix that number with `!`.

## Environment Variables

In class you were shown how the `env` command will echo out numerous values about you (the user) and your session (in `bash`). Run that command again:

```
env
```
There are approximately 60 environment variables set within the Google Shell. Let's use `grep` to find a specific one named `USER`:

```
env | grep USER
```
This returns two environment variables. If we want to use the `USER` variable (our Google username) it can be printed out by calling it as a `bash` variable:

```
echo $USER
```

Now let's set a new variable called `FAVORITE_ICE_CREAM`. Feel free to put your favorite flavor as the value:

```
FAVORITE_ICE_CREAM="salted caramel"
```

You have now set an `env` variable within your session. Try calling it with an `echo` command:

```
echo $FAVORITE_ICE_CREAM
```

However, as we pointed out in class, if you were to close your Google Shell and come back later, this variable would no longer be set. In order to set it permanently it must be stored someplace.

The best place to store an `env` variable, for the `bash` shell, is in the hidden file named `.bashrc`. So let's edit that using `nano`:

```
# Reference the home directory using ~ before the name in case we
# are not in that directory at the moment.
nano ~/.bashrc
```

Using your arrow keys, move down to the empty space below the first three lines, and export your same `env` variable:

```
export FAVORITE_ICE_CREAM="salted caramel"
```

Save and close the file in `nano` by pressing Ctrl+O and then Return, then Ctrl+X and then Return. This will both persist (save) and publish your variable to all your `bash` sessions.

Finally, to refresh your `bash` shell to use that variable, `source` that file. Sourcing triggers your shell to re-process the contents of `.bashrc`:

```
source ~/.bashrc
```

Test it out by echoing the `env` variable you created:

```
echo $FAVORITE_ICE_CREAM
```

##  Quiz Time. 
Great let's answer a couple of quiz questions. To make sure that you are comfortable with the terminal. 

Finally submit a screenshot of your Cursor IDE proving that you have correctly set everything up. 