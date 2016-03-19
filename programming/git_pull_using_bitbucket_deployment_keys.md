# Git Pull Using Bitbucket Deployment Keys

os: ubuntu.

  tested connection using `ssh -T git@bitbucket.org`. then, tried to do git pull using `sudo git pull` but it shows `Permission denied (publickey)`. my bad, i only add public key of my username but haven't add the public key of root. obviously that is why it shows `Permission denied (publickey)`. 


