---
title: Not if, but when
date: "2012-01-09"
url: /blog/2012/01/09/not-if-but-when/
categories:
  - Databases
---
As a MySQL  consultant, I spend a lot of time talking with people about their backups. More specifically, we talk a lot about recovery. I had an interesting incident myself, which illustrates some of the things that are bound to happen as time passes. 

First, let me explain how I do my personal backups. I have a series of external hard drives, which are fully encrypted, as is my computer's hard drive. I maintain a full mirror of my computer's hard drive on these external hard drives. I occasionally switch the hard drives out, and carry one or more of them to a bank's safe deposit box. I try to do this once a week, but sometimes it isn't quite that often. 

As a result, I have one hard drive located physically near my computer, which contains a very recent backup of all my work. I have at least one, usually 3 or more, other copies of my data in a slightly less fresh format, but durably stored in a bank. 

While setting up a new computer recently, I somehow corrupted a GPG-encrypted file that I use quite often, and update frequently. (Perhaps a quantum bit flip or a solar flare---I don't use ECC server-grade RAM, so this is actually possible/likely). As a result, I needed to get my most recent backup. I plugged in my external hard drive, and the drive physically failed. I spent some time doing diagnostics, and concluded that the drive really had failed. This reminded me that I had another hard drive, which I had set aside on a shelf couple of weeks ago, because it had also apparently failed. I pulled this drive off the shelf and ran diagnostics on it. It was also bad. 

So I had lost my most recent copy of my file, as well as my most recent backup of it. it I could go to the bank and retrieve my previous backup of it, but that was a couple of weeks old, and I knew there were some changes that were not in that copy. 

The happy ending to this story is that the corruption was only in the tail of the file, actually only in the last couple of bytes.  I was able to decrypt everything except the last block or so, and then I retrieved that  portion from my old backup. So  in the end, I did not lose any data, but it was an interesting exercise. 

The most interesting thing about this is the probability of several failures happening together. I think it is a natural human tendency to underestimate the probability of several different kinds of failures, or even several identical failures, happening at the same time.  It quite commonly happens that hard drives fail at the same time, and we know that backups fail, and we know that  files are corrupted or deleted, and it's not a matter of if, but when these things happen together. This is why I have several copies of my backups in different places. 

I'm still glad that I do backups the way that I do, keeping my own backups instead of relying on some online backup provider. I have heard many horror stories about them, and witnessed a few myself.  I do not trust anyone else with my backups.


