# Helper for Git
≡ Little guide on how to use Git.

> **Vocabluary**
>
> `Git` - version control system, tracks changes of file.<br>
> `Repository` - folder with files and Git settings, located in hidden **.git** folder.<br>
> `Local repository` - repository located on your computer.<br>
> `Remote repository` - file storage in remote server, such as GitHub. BitBucket, GitLab.<br>

## Local repository

Git commands for **local repository**:
1. `git init` - to initialize in working directory a local repository. This file will be called *.git*. His may delete by using command `rm -r .git`.
2. `git add .` or `git add -all` or `git add <file name>` - this command tracks files, prepares their to storage.
3. `git commit -m "write what about commit" ` - to save changes of project, don't forget to write description of your commit.

## Remote repository

First of all, you need to make a remote repository, then link it with a local repository.
1. Go to [GitHub.com](https://github.com/) and sign up.
2. Connect local and remote repositories using [SSH](https://ru.wikipedia.org/wiki/SSH 'Secure Shell Protocol'). It consists of pair keys: private and public. Let's make their!

## Generation SSH and adding public key to GitHub

To generate SSH, use command <br>
`ssh-keygen -t ed25519 -C "here write your registration mail in GitHub"`.

For coping public key to clipboard, write `clip < ~/.ssh/id_ed25519.pub`, then paste in your GitHub account.
1. Sign in GitHub.com;
2. open item **Settings** in avatar menu;
3. find item **SSH and GPG keys**, press the button `New key`;
4. fill <u>title</u> of key, in key type choose <u>authentification key</u> and paste in area <u>key</u> your clipboard.
Now, SSH-key is linked with GitHub. To check it, write command `ssh -T git@github.com`.

## Linking remote and local repositories

1. In page of remote repository *choose type SSH* and *copy link*;
2. open console of the project directory;
3. enter command `git remote add origin <paste link of remote repository>`

<u>origin</u> - name of remote repository, which has a link from your GitHub repository.
> To ensure that local and remote repositories are linked, use command `git remote -v`. (-v means --verbose).

## Congradilations!
Remote and local repositories are linked with each other.<br>
Now you can share your project with the world!
> To do this, write following command - `git push -u origin main` for the first sending, to the next ones use `git push`.