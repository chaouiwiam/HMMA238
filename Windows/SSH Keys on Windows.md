## Getting Git for Windows

- Download Git Bash [here](https://gitforwindows.org/)
- Launch the installer with the recommended parameters

----

## Creating and setting up an SSH key

- Open Git Bash
- Type `cd ~/.ssh`
- Generate an SSH key :
  - Type `ssh-keygen -t rsa -C "your.email@adress.com"` (with the email adress associated to your GitHub account !!).
  - You should see this : `Enter file in which to save the key (/d/Users/YourUserName/.ssh/id_rsa):`. You already are where you want to be so you can just press `Enter`.
  - You should then be asked for a passphrase : `Enter passphrase (empty for no passphrase):`. Just press `Enter`.
  - You are asked for your passphrase again : `Enter same passphrase again:`. Press `Enter` again. (Note : you can enter a password but If you do so, you will be asked for it any time you push something to GitHub...) You just created both `id_rsa` and `id_rsa.pub` files.
- Display the content of your `id_rsa.pub` file typing `less id_rsa.pub`. You see a continuum of creepy caracters -it's normal. Select the content, exactly as it appears, with no extra spaces or lines, and right-click on it. Then click on `Copy`.
- Now go on to your GitHub account. In the upper-right corner of any page, click on your profile photo, then click on **Settings**.
- In the user settings sidebar on the left, click on **SSH and GPG keys**.
- Click on **New SSH key**.
- In the "Title" field, add a descriptive label for your new key.
- Paste your key into the "Key" field.
- Click on **Add SSH key**.
- Confirm your GitHub password.
- ...you're done !

----

## Testing your SSH key

- Create a new repositoty :
  - On your GitHub main page, that should be located here : `https://github.com/YourUserName`, click on **Repositories**.
  - Click on **New** and give your new repository a name, say "My_first_repo". In the *Initialize this repository with:* section, select **Add a README file** and finally click on **Creat repository**.
- After that you should automatically be located on your new repository. Click on the green **Code** button and select **SSH**. Copy the link and go back to your Git Bash terminal.
- Type `cd ..` to quit your `.ssh` directory.
- Type `git clone` and then paste (after a *space*) the link you just copied (right-click and select **Paste**). It should look something like this : `git clone git@github.com:YourUserName/My_first_repo.git`. Press `Enter`. (Note : If you chose to put a passphrase, you are asked for it : `Enter passphrase for key '/d/Users/Vamelie/.ssh/id_rsa':` so type your passphrase and press `Enter`, otherwise you might see this `Are you sure you want to continue connecting (yes/no/[fingerprint])?` so just type `yes`).
- Change directory to your fresh cloned repository : `cd My_first_repo/`
- Type `code .` to open VScode with the current repository. (Note : if you don't have VScode installed on your machine you can open any other IDE or even a text editor)
- Once you're on VScode, make some quick change on your repository, for example, open the **README** file and add some lines to it. Save your changes (use `Ctrl + S` !).
- Go back to the Git Bash terminal and type `git status`. Press `Enter`. It should say that the **README** file has been modified.
- Type `git add README.md` then `Enter`.
- Type `git status` again (optionnal but personally satisfying). Press `Enter`. You are told that you have changes to be commited.
- Type `git commit -m "any meaningful message"` and press `Enter`.
- Type `git push origin main`, where "main" should be the name of your current branch -if you did not created a new one, by default, you are on the "main" branch. Otherwise type `git push origin the_name_of_your_branch`. Press `Enter`.
- Go back to GitHub and refresh the page. You should see your changes.