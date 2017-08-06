# Notes

* no need to create an API user, use the credentials I sent in the email
* after you use `setup_p2.sh` script to create an instance, go to AWS Console, select it, click Action, click Add/Edit Tags, prepend your nickname to Name of instance so that you can easily find it on the list of instances when others add their own
* reboot after first SSHing into instance, so nvidia is propertly set up


# Don’t break your dev python env by not installing Anaconda as root Python

* install anaconda with GUI instaleld
* comment out anaconda PATH in `~/.bash_profile`
* create a conda isolated env: `~/anaconda/bin/conda create --name course`
* activate the env: `source ~/anaconda/envs/course/bin/activate`

Let's verify. Run the following in the terminal:

```bash
(root) course$ which python
/Users/zupo/anaconda/bin/python
```

Run this in a new terminal window. Python path should be to your system Python, not to Anaconda's:

```bash
course$ which python
/usr/local/bin/python
```


# Don't overwrite existing AWS config

If you already used awscli in the past, you have configuration and credentials already set, and blindly following the course will make you overwrite them.

* edit `~/.aws/config` and change `[default]` to `[profile original]` (or similar)
* do the same for `~/.aws/credentials`
* now whenever you need your original config/credentials, run aws with `--profile original`
