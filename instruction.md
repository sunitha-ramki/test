setup ssh b/w local and github
1. in gitbash run cmd 
ssh-keygen -t ed25519 -C "sunitha.ramki@gmail.com"

check .ssh path 
C:\Users\Sunitha\.ssh

STEPS FROM Google
To connect Git Bash to your personal GitHub account using SSH, you need to generate an SSH key pair, add the key to the local background agent, and upload the public key to GitHub. [1, 2]  
1. Generate a New SSH Key [1]  
Open Git Bash and execute the following command to generate a secure Ed25519 key pair. Replace the placeholder text with your primary GitHub email address: 

• Save File: When prompted to "Enter a file in which to save the key," press Enter to accept the default file location (). 
• Passphrase: Type a secure passphrase and press Enter, then retype it to confirm. You can also leave this blank by pressing Enter twice, though a passphrase is recommended for security. [3, 6]  

2. Add the SSH Key to the ssh-agent [1]  
Turn on the background SSH agent to securely store your credentials so you do not have to type your passphrase every time: [2, 7, 8, 9]  
3. Copy the Public Key to Clipboard [10]  
Run this command to print your public key string directly in the Git Bash window: [2, 4]  
Select the entire printed line (starting with  and ending with your email), right-click, and choose Copy (or use  in Git Bash). [4, 11, 12, 13]  
4. Link the Key to Your GitHub Account 

1. Log in to your personal account on the  GitHub Website . 
2. Click your profile photo in the upper-right corner and select  GitHub Account Settings . 
3. On the left sidebar menu, click SSH and GPG keys. 
4. Click the green New SSH key button. 
5. In the Title box, type a clear nickname (e.g., "Personal Windows Laptop"). 
6. Leave the Key type as Authentication Key. 
7. Paste your copied string into the Key box and click Add SSH key. [2, 11, 14, 15, 16]  

5. Verify the Connection 
Test that your configuration works by reaching out to GitHub over SSH: 

• You will see a warning stating: "The authenticity of host 'github.com (...)' can't be established." 
• Type  and hit Enter. 
• The terminal will output:  [4, 18, 19, 20, 21]  

If you want, tell me: 

• Are you setting up multiple GitHub accounts on this same machine? 
• Are you looking to convert an existing local repository from HTTPS to SSH? 

I can provide the specific configurations or commands to handle those setups. 

AI responses may include mistakes.

[1] https://docs.github.com/en/authentication/connecting-to-github-with-ssh
[2] https://decodementor.medium.com/connect-git-to-github-using-ssh-68ab338f4523
[3] https://docs.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
[4] https://dev.to/sharon_m/connecting-git-bash-to-github-a-beginners-guide-4lb0
[5] https://blog.lawrencemcdaniel.com/deploy-from-a-private-github-repo/
[6] https://www.geeksforgeeks.org/git/using-github-with-ssh-secure-shell/
[7] https://www.datacamp.com/tutorial/ssh-keys
[8] https://www.educative.io/answers/how-to-solve-permission-denied-public-key-error-when-using-git
[9] https://www.reddit.com/r/git/comments/ycp1oi/how_does_the_git_user_system_work/
[10] https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/GitHub-SSH-Key-Setup-Config-Ubuntu-Linux
[11] https://gist.github.com/xirixiz/b6b0c6f4917ce17a90e00f9b60566278
[12] https://www.youtube.com/watch?v=0YFQwGB-tIg
[13] https://windowsforum.com/threads/install-git-on-windows-11-quick-setup-guide-with-git-bash-and-lfs.385707/
[14] https://docs.github.com/articles/adding-a-new-ssh-key-to-your-github-account
[15] https://www.gitkraken.com/learn/git/problems/github-add-ssh-key
[16] https://codingnomads.com/generate-github-personal-access-token-github-ssh-key
[17] https://docs.github.com/en/authentication/troubleshooting-ssh/using-ssh-over-the-https-port
[18] https://www.youtube.com/watch?v=9gkb81GKmVI
[19] https://coderefinery.github.io/installation/ssh/
[20] https://github.com/cs1302uga/cs1302-tutorials/blob/master/github-setup.md
[21] https://www.theodinproject.com/lessons/foundations-setting-up-git


===========================================================================================




Sunitha@DESKTOP-OBHNM51 MINGW64 ~
$ eval "$(ssh-agent -s)"
Agent pid 1516

Sunitha@DESKTOP-OBHNM51 MINGW64 ~

Sunitha@DESKTOP-OBHNM51 MINGW64 ~
$ ssh-add ~/.ssh/id_ed25519
Identity added: /c/Users/Sunitha/.ssh/id_ed25519 (sunitha.ramki@gmail.com)


Sunitha@DESKTOP-OBHNM51 MINGW64 ~
$ cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJUFXW1a+b+d/jjla6WiDMmE6nm8hDe0D1uqnBnUysLP sunitha.ramki@gmail.com

Sunitha@DESKTOP-OBHNM51 MINGW64 ~

ssh -T sunitha.ramki@github.com

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
New repo insturction from github

sunitha: When cloned test repo it was new so github gave me these instructions
…or create a new repository on the command line
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:sunitha-ramki/test.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin git@github.com:sunitha-ramki/test.git
git branch -M main
git push -u origin main



=====================



git config --global user.email "sunitha.ramki@gmail.com"
git config --global user.name "Sunitha Ramakrishnan"

+++++++++++++++++++++++++++++++++++++++++++++
Formatting .md
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax