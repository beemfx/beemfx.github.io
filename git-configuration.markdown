---
layout: page
title: "Git Configuration"
permalink: /git-configuration/
---
<!-- wp:preformatted -->
<pre class="wp-block-preformatted">[user]<br>name = USERNAME<br>email = email@email.com<br>[diff]<br>tool = p4merge<br>[difftool p4merge]<br>cmd = p4merge.exe $LOCAL $REMOTE<br>[merge]<br>tool = p4merge<br>[mergetool p4merge]<br>cmd = p4merge.exe $BASE $LOCAL $REMOTE $MERGED<br>trustExitCode = true<br>keepBackup = false </pre>
<!-- /wp:preformatted -->
