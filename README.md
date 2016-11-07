# aws-ssh

Easily log into Elastic Beanstalk instances that are sitting behind bastion
hosts.

## TODO

* support OpsWorks instances
* support non-Amazon Linux boxes (ec2-user is currently hard-coded)

## Requirements

* [AWS CLI](https://aws.amazon.com/cli/)

## Usage

Your Elastic Beanstalk project must already be set up with a
`.elasticbeanstalk/config.yml` file.

From your Elastic Beanstalk project directory:

```shell
$ aws-ssh -b <bastion hostname> <Elastic Beanstalk environment name>
```

You will need to have the ssh key used to log into both the bastion host
and the Elastic Beanstalk host available to ssh. The easiest way to do
this is to use `ssh-add` to add it to your agent. On a Mac, you can do:

```shell
$ ssh-add -K <private key>
```

This will add your private key to your keychain and should make it always
available for use.
