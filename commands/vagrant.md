[Vagrant](http://www.vagrantup.com/)

### Adding box

```
vagrant box add ubuntu/trusty64
```

Box is downloaded to `~/.vagrant.d/boxes` directory.

### Initializing Vagrantfile

```
vagrant init
```

### Starting machine

```
vagrant up
```

### SSH into running machine

```
vagrant ssh
```

### Stopping machine

```
vagrant halt
```

### Destroying machine

```
vagrant destroy [-f]
```