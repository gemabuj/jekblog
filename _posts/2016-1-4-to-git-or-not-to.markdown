---
layout: post
title:  "To Git or not to Git, that is the question"
date:   2016-1-4 13:46:30 +0700
categories: jekyll update
---

{% highlight git %}
git init
git status
git add .
git commit -am "your_commit_message"
git remote add origin your_git_repository_ssh
git push -u origin master
{% endhighlight %}

Sometimes, an unexpected error occured. Shit happens. `"Help, I keep getting a 'Permission Denied (publickey)' error when I push!"`. This means, on your local machine, you haven't made any SSH keys. Not to worry. Here's how to fix:

1. Open git bash (Use the Windows search. To find it, type "git bash") or the Mac Terminal. __Pro Tip:__ You can use any `*nix` based command prompt (but *not* the default Windows Command Prompt!)

2. Type `cd ~/.ssh`. This will take you to the root directory for Git (Likely `C:\Users\[YOUR-USER-NAME]\.ssh\` on Windows)

3. Within the `.ssh` folder, there should be these two files: `id_rsa` and `id_rsa.pub`. These are the files that tell your computer how to communicate with GitHub, BitBucket, or any other Git based service. Type `ls` to see a directory listing. If those two files don't show up, proceed to the next step. __NOTE:__ Your SSH keys must be named `id_rsa` and `id_rsa.pub` in order for Git, GitHub, and BitBucket to recognize them by default.

4. To create the SSH keys, type `ssh-keygen -t rsa -C "your_email@example.com"`. This will create both `id_rsa` and `id_rsa.pub` files.

5. Now, go and open `id_rsa.pub` in your favorite text editor (you can do this via Windows Explorer or the OSX Finder if you like, tpying `open .` will open the folder).

6. Copy the contents--exactly as it appears, with no extra spaces or lines--of `id_rsa.pub` and paste it into GitHub and/or BitBucket under the Account Settings > SSH Keys. __NOTE:__ I like to give the SSH key a descriptive name, usually with the name of the workstation I'm on along with the date.

7. Now that you've added your public key to Github and/or BitBucket, try to `git push` again and see if it works. It should! In case you don't remember the syntax, here it is:

{% highlight git %}
git push -u origin master
{% endhighlight %}

More help available from [GitHub on creating SSH Keys][ssh] and [BitBucket Help][bitbucket].

[ssh]: https://help.github.com/articles/generating-ssh-keys
[bitbucket]: https://confluence.atlassian.com/display/BITBUCKET/Troubleshooting+SSH+Issues
