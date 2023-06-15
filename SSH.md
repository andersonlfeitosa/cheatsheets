## SSH

This is a little cheatsheet about [SSH](https://en.wikipedia.org/wiki/Secure_Shell).

### Create an SSH key pair

To create an SSH key pair:

Open a terminal and navigate to your home or user directory using cd, for example: cd ~

Generate a SSH key pair using ssh-keygen, such as:
```
ssh-keygen -t ed25519 -b 4096 -C "{username@emaildomain.com}" -f {ssh-key-name}
```

Where:
- {username@emaildomain.com} is the email address associated with the Bitbucket Cloud account, such as your work email account.
- {ssh-key-name} is the output filename for the keys. We recommend using a identifiable name such as bitbucket_work.

When prompted to Enter passphrase, you can either provide a password or leave the password empty. If you input a password, you will be prompted for this password each time SSH is used, such as using Git command that contact Bitbucket Cloud (such as git push, git pull, and git fetch). Providing a password will prevent other users with access to the device from using your keys.

Once complete, ssh-keygen will output two files:

{ssh-key-name} — the private key.

{ssh-key-name}.pub — the public key.


### To ensure the correct SSH

To ensure the correct SSH key is used when connecting to Bitbucket, update or create your SSH configuration file (~/.ssh/config) with the following settings:

```
Host bitbucket.org
  AddKeysToAgent yes
  IdentityFile ~/.ssh/{ssh-key-name}
```  
  
### Check that your SSH authentication works
To test that the SSH key was added successfully, open a terminal on your device and run the following command:
```
ssh -T git@bitbucket.org
```

If SSH can successfully connect with Bitbucket using your SSH keys, the command will produce output similar to:

```
authenticated via ssh key.

You can use git to connect to Bitbucket. Shell access is disabled
```
