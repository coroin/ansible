# coroin/apb

A Docker container to automate provisioning using the [ansible](https://www.ansible.com/) command `ansible-playbook`.

### Installation

Pull the latest version from the Docker registry:

```
$ docker pull coroin/apb
```

### Build

To build the image from source:

```
$ git clone https://github.com/coroin/apb.git
$ cd apb
$ sudo docker build -t coroin/apb .
```

### Usage Examples

The following examples run `ansible-playbook` commands:

Echo "Hello World", using playbook called `hello-world.yml` in the `./examples` folder:

```
$ sudo docker run --rm -v `echo $PWD`:/project coroin/apb ./examples/hello-world.yml
```

*Note: `docker -v` requires an absolute-path, so we use `echo $PWD` to send the present-working-directory to bash.*

Ping the localhost, using playbook called `ping.yml` in the `./examples` folder:

```
$ sudo docker run --rm -v `echo $PWD`:/project coroin/apb ./examples/ping.yml
```
