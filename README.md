# docker-openfalcon-judge

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-judge .
```

## Run

### Basic Run

Use default configuration, and falcon-judge package.

```
$sudo docker run -dti --name judge -p 6080:6080 -p 6081:6081 openfalcon-judge
```

### Advanced Run

+ Self-defined configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Judge](http://book.open-falcon.com/zh/install/judge.html).

+ New falcon-judge package

    Replace file **falcon-judge.tar.gz** in the volume */package*.
  
For example, **cfg.json** in /tmp/config and **falcon-judge.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name judge -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 6080:6080 -p 6081:6081 openfalcon-judge
```
