---
layout: post
title: "Running and testing puppet master locally"
date: 2013-12-25 13:33
comments: true
categories: ["Automate everything", "Puppet", Testing]
---
About a month ago we started to use [Puppet](http://puppetlabs.com/) at [Magnet.me](http://magnet.me). Puppet automates all our server provisioning from our dev server, to the Raspberry Pi we have running at the office. We learned most of the setup from the [Pro Puppet][pro-puppet] book, and [GitHub's talk about puppet](http://www.youtube.com/watch?v=4iTBs2S_im8). While reading all the documentation, we could not find any information about developing Puppet manifests locally and testing them on local copies of the machines. As a result, we ended up editing the Puppet manifests directly over an SSH connection. this prevented us from doing a nice pull-request flow and caused and broke some of the operational nodes. In this blog post, I will explain the solution we came up with after that.

<!--more-->

This blog post assumes you have a running Puppet master with the configuration in `/etc/puppet/` which is also a Git repository. You should also have [Vagrant](http://vagrantup.com) and [VirtualBox][pro-puppet] installed. If you're trying to figure out how to set-up a Puppet master and slaves I highly recommend the [Pro Puppet](http://it-ebooks.info/book/730/) book.

- Explain the vagrant file
- /etc is mounted to the vbox folder
- puppet apply sets-up the proper host
- now add a host and try that one

- Disclaimer that this is self-though-off. Feedback for a better solution is always welcome.

- Next steps: try to provision every type of host on the build server, whenever you change something, so we see the build status at the PR.

[pro-puppet]: http://it-ebooks.info/book/730/  "Pro puppet book"