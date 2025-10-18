---
layout: page
title: "Git Configuration"
permalink: /git-configuration
---
{% highlight bash %}
[user]
name = USERNAME
email = email@email.com
[diff]
tool = p4merge
[difftool p4merge]
cmd = p4merge.exe $LOCAL $REMOTE
[merge]
tool = p4merge
[mergetool p4merge]
cmd = p4merge.exe $BASE $LOCAL $REMOTE $MERGED
trustExitCode = true
keepBackup = false
{% endhighlight %}