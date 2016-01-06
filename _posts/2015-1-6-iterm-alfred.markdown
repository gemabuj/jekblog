---
layout: post
title:  "A Failed Integration between AlfredApp and iTerm"
date:   2015-12-28 11:46:30 +0700
categories: jekyll update
---

So basically i'm quite happy with alfredapp, but too bad that below script to integrate alfred and iTerm seems need a little tweak to work properly.

{% highlight applescript %}
-- This is v0.4 of the custom script for AlfredApp for iTerm 2.1.1
-- Please see https://github.com/stuartcryan/custom-iterm-applescripts-for-alfred/
-- for the latest changes.

-- Please note, if you store the iTerm binary in any other location than the Applications Folder
-- please ensure you update the two locations below (in the format of : rather than / for folder dividers)
-- this gets around issues with AppleScript not handling things well if you have two iTerm binaries on your system... which can happen :D

on alfred_script(q)
	if application "iTerm" is running then
		run script "
			on run {q}
				tell application \":Applications:iTerm.app\"
					activate
					try
						set myterm to the first terminal
					on error
						set myterm to (make new terminal)
					end try
					tell myterm
						set mysession to (launch session \"Default Session\")
						tell mysession to write text q
					end tell
				end tell
			end run
		" with parameters {q}
	else
		run script "
			on run {q}
				tell application \":Applications:iTerm.app\"
					activate
					tell the first terminal
						tell the last session to write text q
					end tell
				end tell
			end run
		" with parameters {q}
	end if
end alfred_script
{% endhighlight %}