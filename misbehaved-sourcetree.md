Here is, after like one month with my sourcetree keep asking for password everytime I want to push my code, finally it becomes normal again.

It began when I installed regular update of my sourcetree, about one or two months ago. Since then, everytime I wanted to push code to my repo \(bitbucket, github & gitlab\), sourcetree will ask for my password. And as expected, it quickly becomes annoying.

Not long after, I realized that the keep-asking-for-password behaviour is not the only thing affected. Turns out that I don't get any pull notification anymore. I'd to manually hit that pull button in sourcetree to check if there's something to pull from my repo. Annoying.

After some googling, turns out that changing repo's remote url from https to ssh fixed above annoying behaviour. However, using ssh to push is not an option for me: my university network has blocked ssh. Which means, if I use ssh, I won't be able to get pull notification nor push my code when using university network.

I almost gave up with sourcetree, and been using terminal to push the code because it doesn't require me to type my password again and again everytime I push my code. Using terminal is a bit difficult to me when I've to manage and check a lot of changes in repo.



Last night, didn't know why but I googled again about the issue and found in a forum about sourcetree option to change git binary being used. That post reminds me that I there's configuration in sourcetree to select which git binary to use; the embedded one by sourcetree, or the one installed by system.

I open the configuration and saw that my sourcetree is set to use embedded version of git. Without thinking much, I changed the configuration from using embedded version to using git installed by system. Configuration saved, and tried to push my code using sourcetree. Yay! It doesn't ask for password. Even the pull notification is back! Well.. if only I knew about this sooner, I wouldn't have to type my password everytime I push my code. And also, I wouldn't have to press that \`Pull\` button only to check if my team mate pushed new commit.

Anyway, that's the story of me with sourcetree. And moral of the story is, sometimes it's just misconfiguration and not an error. Till next!

