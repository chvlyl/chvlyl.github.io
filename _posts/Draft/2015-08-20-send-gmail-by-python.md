---
layout: post
title: "Send gmail by python"
date: 2015-08-20
---

### Install pip from [here](https://pip.pypa.io/en/latest/installing.html)

### Install yagmail.
pip install yagmail

### Turn on less secure app
https://www.google.com/settings/security/lesssecureapps

import yagmail
yag = yagmail.SMTP('user_me@gmail.com')
yag.send('user_you@gmail.com', 'Why,Oh why!')

