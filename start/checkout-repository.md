# Checkout Repository

Git repositories are a way to track changes to the codebase, this is useful in case bugs are introduced you can look back at all the changes that were committed to the repository. Think of when you hit "save' in a Word document, except that each time you hit save you get a new "copy" of the document and can look back through each time you hit save to see the differences.

1. Navigate to https://github.com/jbaldwin/learn-typescript
2. Click on the green "Code" button, this will give a dropdown on how to `clone` the repository locally to your computer.
3. Under `Local` chose `HTTPS` and then copy the url, it should look like: https://github.com/jbaldwin/learn-typescript.git
4. Open your `Git Bash` locally on your computer.
5. Type `ls` and then enter to list the current contents of the current directory you are in. `ls` is a linux command available in `Git Bash` that lists the contents of the current directory. You should be in your "Home Directory".  It shoudl display something similar to:

```bash
joshr@GoobToob MINGW64 ~
$ ls
 AppData/             NTUSER.DAT                                                                                     Recent@
'Application Data'@   NTUSER.DAT{e5243cf1-1aac-11ee-a364-dc4628690cd9}.TxR.0.regtrans-ms                            'Saved Games'/
 Contacts/            NTUSER.DAT{e5243cf1-1aac-11ee-a364-dc4628690cd9}.TxR.1.regtrans-ms                             Searches/
 Cookies@             NTUSER.DAT{e5243cf1-1aac-11ee-a364-dc4628690cd9}.TxR.2.regtrans-ms                             SendTo@
 Desktop/             NTUSER.DAT{e5243cf1-1aac-11ee-a364-dc4628690cd9}.TxR.blf                                      'Start Menu'@
 Documents/           NTUSER.DAT{e5243cf2-1aac-11ee-a364-dc4628690cd9}.TM.blf                                        Templates@
 Downloads/           NTUSER.DAT{e5243cf2-1aac-11ee-a364-dc4628690cd9}.TMContainer00000000000000000001.regtrans-ms   Videos/
 Favorites/           NTUSER.DAT{e5243cf2-1aac-11ee-a364-dc4628690cd9}.TMContainer00000000000000000002.regtrans-ms   ansel/
 Links/               NetHood@                                                                                       ntuser.dat.LOG1
'Local Settings'@     OneDrive/                                                                                      ntuser.dat.LOG2
 Music/               Pictures/                                                                                      ntuser.ini
```

Each entry you see in the output is a file or directory that is in the current directory, `ls` will also show a lot of files that windows normally hides from you, so if you navigated via the windows `File Explorer` GUI (graphical user interface) you probably won't see a lot of these files normally without forcing Windows by using "Show hidden files or folders" option.

1. Type `pwd` and hit enter, this command is the present working directory and will give you the current path that the terminal is working in. It should display something like:

```bash
joshr@GoobToob MINGW64 ~
$ pwd
/c/Users/joshr
```

* `/c` means we are on the windows `C:` drive, its been 'linuxified' so its just `/c`.
* `/Users` means we are in the Users directory under the C drive.
* `/joshr` is my home directory.

In the terminal `~` is shorthand for the home directory. As you can see the terminal prompt is : `joshr@GoobToob MINGW64 ~` this is the user, me, @ GoobToob, my computer name, using MINGW64 "windows prompt" and the terminal is currently in the `~` home directory. `~` in this case is equivalent to `/c/Users/joshr`.

6. Create a new directory called `repos`, repos is short for `repositories`, I generally like the shorthand so its a little less to type. To create this run `mkdir repos`.  `mkdir` is another command which stands for "make directory" and the name after it is the name of the directory we want to create.
7. Execute the `ls` command again and you should now see the `repos` directory has been created.
8. Lets move into the newly created repos directory. To do this execute the `cd repos` command. `cd` is the "change directory" command and it tells the terminal to move the working directory into the named directory.
    * `.` (dot) is a special directory for the "current" directory.  If you run `cd .` it "moves" you into the same directory you are currently in, doesn't do much here but its worth noting what the special `.` file means.
    * `..` (dot dot) is also a special directory and it stands for the parent directory that you are currently in. The parent directory of `repos` is your home directory, so by typing `cd ..` it will move you back up to the `~` directory. This is important since it lets you move up and down the directory hierarchy.
    * `-` is a special `cd` argument which means "move to the last directory I was in. So issuing `cd -` will change your working directory to the last directory you were in. If you issue this twice in a row it will keep changing the directory from the two last directories you were in, try it now and it should keep flipping you between your home directory and the repos directory.
    * After trying all of these lets make sure we are in the newly created `repos` directory, use the newly learned commands to get there and show that you are in that directory.
9. Clone the git repository. To do this we want to run `git clone <url>` where `<url>` is the URL we copied from step (3). This will issue a `clone` command to `git` and fetch the remote repository locally.
    * `git clone https://github.com/jbaldwin/learn-typescript.git`
    * Execute `ls` and you should see it created a new directory `learn-typescript`, lets `cd` into that directory and then you should be able to `ls` all the files that are in the repo locally.
10. Open VS Code and then File -> Open Folder the `/c/Users/<user>/repos/learn-typescript` directory so we can start coding.
11. Proceed to [lesson-001](../lessons/lesson-001/hello-world.md) now that you have the repository locally cloned and have it opened in VS Code!
 