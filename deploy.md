### SSH Deploy keys
- Generate a pair of deploy keys with `ssh-keygen`
- Put them into ~/.ssh directory and `chmod 600`
- Create `~/.ssh/config` file and folowing configuration

  ```
  Host github.com
    Port 22
    IdentityFile ~/.ssh/<your private key name>
  ```

- Go to github project settings and add public key to 'deploy keys'
