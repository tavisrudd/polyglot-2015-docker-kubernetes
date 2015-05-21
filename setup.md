<article class="markdown-body">
<link rel="stylesheet" href="github-markdown.css">
<style>
.markdown-body {
  min-width: 200px;
  max-width: 790px;
  margin: 0 auto;
  padding: 30px;
}
</style>

# Google Compute Engine

## Account setup

Sign up for a free trial account at [https://cloud.google.com/compute/](https://cloud.google.com/compute/).
If you already have an active account, contact us and we'll get you some free credits.



## Command line `gcloud` SDK

### Installation
Windows users see section 1 of [these instructions](https://docs.google.com/document/d/1e3h2uqlSDAAL9oyukzBMz24vEaQ0KA7qKRMCJJ-v4Ns/edit#heading=h.rbowbg87qipb)

Everyone else, do this on your laptop:
```sh
$ curl https://sdk.cloud.google.com | bash
```

and then open a new terminal so your environment variables / $PATH will be
correct.

Then
```sh
$ gcloud components update
$ gcloud components update alpha
```

### Auth
```sh
$ gcloud auth login
$ gcloud config set compute/zone us-central1-c

```

### Configuration

Use your web-browser to create a new project on GCE: https://console.developers.google.com/project and
then

```sh
$ your_project="whatever GCE gave you for it's ID..."
$ gcloud config set project $your_project
```


### Create your docker host vm
```sh
$ gcloud compute instances create launchpad --image debian-7-backports --machine-type n1-standard-1
$ gcloud compute instances list # make a note of the public ip

```

Configure the network / firewall

```sh
$ gcloud compute firewall-rules create workshop --allow=tcp:80,tcp:8070-8090,tcp:9200,tcp:9292

```

Ssh into your vm:
```sh
$ gcloud compute ssh launchpad
```

Once logged in to the vm:
```sh
$ sudo su - # we'll stay as root for the rest
$ curl -sSL https://get.docker.com/ | sh
$ apt-get install htop jq curl screen tmux
$ apt-get install vim nano emacs # pick your poison
```

We'll be running our shells on the vm inside your choice of `screen`
or `tmux` in case our local network is flaky. Start a `screen` or
`tmux` session now and run the remaining commands inside it.


```sh
$ curl -L https://github.com/docker/compose/releases/download/1.2.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
$ chmod +x /usr/local/bin/docker-compose

```

```sh
apt-get install iproute2 cgroup-bin util-linux make psmisc python-dev libncursesw 
wget https://raw.githubusercontent.com/tavisrudd/dockhack/master/dockhack
chmod +x ./dockhack
mv dockhack /usr/local/bin/
dockhack install_deps

wget http://hisham.hm/htop/releases/1.0.3/htop-1.0.3.tar.gz
tar zxf htop-1.0.3.tar.gz
cd htop-1.0.3
./configure; make; make install

```

</article>
