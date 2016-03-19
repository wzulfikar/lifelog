# Git Pull Using Bitbucket Deployment Keys

os: ubuntu.

  tested connection using `ssh -T git@bitbucket.org`. then, tried to do git pull using `sudo git pull` but it shows `Permission denied (publickey)`. my bad, i only add public key of my username but haven't add the public key of root. obviously that is why it shows `Permission denied (publickey)`. 
  
if i want to be able to `sudo git pull`, i must add public key of root to bitbucket deployment keys. 

when i do `git pull`, it shows `error: cannot open .git/FETCH_HEAD: Permission denied`. this error related to the os itself, not bitbucket. to allow my username (ubuntu) access to .git dir, i can do `sudo chown -R ubuntu:ubuntu .git`. now, i can do `git pull` succesfully.


