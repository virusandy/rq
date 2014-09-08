---
title: "Documentation"
layout: contrib
---

### Running docs locally


If you're running these docs on your local machine;

```
sudo apt-get -y install ruby-dev nodejs
sudo gem install jekyll
jekyll serve
```

### Running docs on Vagrant

If you're a [Vagrant](https://www.vagrantup.com/) user;

```
vagrant init ubuntu/trusty64
vagrant up
vagrant ssh -- "sudo apt-get -y install ruby-dev nodejs"
vagrant ssh -- "sudo gem install jekyll"
vagrant ssh -- "(cd /vagrant; jekyll serve)"
```

You'll also need to add a port forward entry to your `Vagrantfile`;

```
config.vm.network "forwarded_port", guest: 4000, host: 4001
```

Then you can access the docs using;

```
http://127.0.0.1:4001
```

You also may need to forcibly kill Jekyll if you ctrl+c;

```
vagrant ssh -- "sudo killall -9 jekyll"
```