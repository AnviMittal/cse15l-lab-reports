# Lab Report 3
# *Anvi Mittal*

[Home](index.html)
<br />
<br />

***

**Streamlining `ssh` Configuration**

When we log into `ieng6`, we must type the command `ssh cs15lsp22ava@ieng6.ucsd.edu` every single time. In order to streamline this process, we can put an entry in `~/.ssh/config` that tells SSH what username to use when logging into a specific server. So, open `~/.ssh/config` and all the following lines in it:

```
Host ieng6
HostName ieng6.ucsd.edu
User cs15lsp22ava (use your own username)
```


By doing this, you can login into `ssh` by simply using the command `ssh ieng6`. For example-
![Image](ssh_ieng6.png)

To copy a file from your laptop to a remote server, we can use the command `scp` and instead of typing out the entire username, all we need to do is use `ieng6` and the file will be copied. 
For example (I have used `scp` to copy the file "Text.md" ) -
![Image](scp.png)

**Setting up Github Access from `ieng6`**

Public key on Github:
![Image](public.png)

Private (id_ed25519) and public (id_ed25519.pub) keys on ieng6 server:
![Image](private.png)

In order to set up github access from the command line, we need to set up a token-based login mechanism like `SSH Keys`. Follow this [tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
to be able to use commands like `git push` directly from the command line. You’ll know you’ve succeeded whenyou can use `git push origin
main` after committing to push your changes to Github from the command line.

It should look something like-
![Image](github.png)

[The commit](https://github.com/AnviMittal/cse15l-lab-reports/commit/699c580f37b44dedf7fbc510587851047cee13e9)

**Copying whole directories with `scp-r`**

Copying markdown-parse directory to ieng6
account:
![Image](markdown.png)

We can see that the directory has been copied below:
![Image](proof.png)

Running some tests on the repository like `make test`:

![Image](runningtests.png)

Now, to make our work easier, I will try and combine commands like below:
![Image](one_line.png)

This gives us the same result as the previous screenshots but in lesser time and with lesser effort. 
![Image](abc.png)

We can use the command `scp` to only copy one file. If we want to copy a whole directory of files, it becomes easier when we use the command `scp-r`. To use `scp-r`: Log into the terminal of the directory you want to copy (I am using my personal username and the directory "markdown-parser") and use the command `scp -r . cs15lsp22@ieng6.ucsd.edu:~/markdown-parser` to copy the entire directory. It will look something like - 
![Image](mark1.png)
![Image](mark2.png)