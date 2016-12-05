# ssh-secure
Tools to automatically fix the sshd/ssh configuration.

After a security scan of your servers you might get warnings like the following:

* SSH Weak Algorithms Supported
* SSH Server CBC Mode Ciphers Enabled
* SSH Weak MAC Algorithms Enabled

This script fixes your server's sshd and ssh config such that the server is follows best practice wrt which ciphers and algorithmns to use

## Howto

To update / check your ssh(d) configuration, fetch the newest version of this script, and run it using Python (2.x)

    wget https://raw.githubusercontent.com/svalgaard/ssh-secure/master/sshd-fix -O sshd-fix
    sudo python sshd-fix

If your sshd daemon is not restarted as part of running sshd-fix, you should do this as soon as possible.
Next, from another session, check that you can still login to server and that everything works as expected.

## But I do not want to run something like this as root (using sudo)?!?

In this case, simply run the script without sudo, and copy-paste the lines to your ssh(d) configuration files.
If you are using a very old version of ssh, you may have to run this as root (possibly via sudo) (or look at the output from `sshd -T` yourself.
