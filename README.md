# Push Verified Commits from the Command Line

Push verified commits from the command line.  Example repo to accompany article.

## Show example of an `unverified` commit (typical dev setup)


## Configure `verified` commits

- Confirm you have ssh access to your account:

```zsh
ssh -vT git@github.com
```

- The above command returns and ssh handshake between your device and GitHub.com

```zsh
ssh -vT git@github.com
OpenSSH_9.0p1, LibreSSL 3.3.6
debug1: Reading configuration data /etc/ssh/ssh_config
debug1: /etc/ssh/ssh_config line 21: include /etc/ssh/ssh_config.d/* matched no files
debug1: /etc/ssh/ssh_config line 54: Applying options for *
debug1: Authenticator provider $SSH_SK_PROVIDER did not resolve; disabling
debug1: Connecting to github.com port 22.
debug1: Connection established.
debug1: identity file /Users/user001/.ssh/id_rsa type -1
debug1: identity file /Users/user001/.ssh/id_rsa-cert type -1
debug1: identity file /Users/user001/.ssh/id_ecdsa type -1
debug1: identity file /Users/user001/.ssh/id_ecdsa-cert type -1
debug1: identity file /Users/user001/.ssh/id_ecdsa_sk type -1
debug1: identity file /Users/user001/.ssh/id_ecdsa_sk-cert type -1
debug1: identity file /Users/user001/.ssh/id_ed25519 type 3
debug1: identity file /Users/user001/.ssh/id_ed25519-cert type -1
debug1: identity file /Users/user001/.ssh/id_ed25519_sk type -1
debug1: identity file /Users/user001/.ssh/id_ed25519_sk-cert type -1
debug1: identity file /Users/user001/.ssh/id_xmss type -1
debug1: identity file /Users/user001/.ssh/id_xmss-cert type -1
debug1: identity file /Users/user001/.ssh/id_dsa type -1
debug1: identity file /Users/user001/.ssh/id_dsa-cert type -1
debug1: Local version string SSH-2.0-OpenSSH_9.0
debug1: Remote protocol version 2.0, remote software version babeld-7e018303
debug1: compat_banner: no match: babeld-7e018303
debug1: Authenticating to github.com:22 as 'git'
debug1: load_hostkeys: fopen /Users/user001/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: SSH2_MSG_KEXINIT sent
debug1: SSH2_MSG_KEXINIT received
debug1: kex: algorithm: curve25519-sha256
debug1: kex: host key algorithm: ssh-ed25519
debug1: kex: server->client cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: kex: client->server cipher: chacha20-poly1305@openssh.com MAC: <implicit> compression: none
debug1: expecting SSH2_MSG_KEX_ECDH_REPLY
debug1: SSH2_MSG_KEX_ECDH_REPLY received
debug1: Server host key: ssh-ed25519 SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU
debug1: load_hostkeys: fopen /Users/user001/.ssh/known_hosts2: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts: No such file or directory
debug1: load_hostkeys: fopen /etc/ssh/ssh_known_hosts2: No such file or directory
debug1: Host 'github.com' is known and matches the ED25519 host key.
debug1: Found key in /Users/user001/.ssh/known_hosts:1
debug1: rekey out after 134217728 blocks
debug1: SSH2_MSG_NEWKEYS sent
debug1: expecting SSH2_MSG_NEWKEYS
debug1: SSH2_MSG_NEWKEYS received
debug1: rekey in after 134217728 blocks
debug1: get_agent_identities: bound agent to hostkey
debug1: get_agent_identities: agent returned 1 keys
debug1: Will attempt key: /Users/user001/.ssh/id_ed25519 ED25519 SHA256:d1IU7r1+0qOrFCNtmhBIlpUs7UvUOqQx0hqIumMQa6M agent
debug1: Will attempt key: /Users/user001/.ssh/id_rsa
debug1: Will attempt key: /Users/user001/.ssh/id_ecdsa
debug1: Will attempt key: /Users/user001/.ssh/id_ecdsa_sk
debug1: Will attempt key: /Users/user001/.ssh/id_ed25519_sk
debug1: Will attempt key: /Users/user001/.ssh/id_xmss
debug1: Will attempt key: /Users/user001/.ssh/id_dsa
debug1: SSH2_MSG_EXT_INFO received
debug1: kex_input_ext_info: server-sig-algs=<ssh-ed25519-cert-v01@openssh.com,ecdsa-sha2-nistp521-cert-v01@openssh.com,ecdsa-sha2-nistp384-cert-v01@openssh.com,ecdsa-sha2-nistp256-cert-v01@openssh.com,sk-ssh-ed25519-cert-v01@openssh.com,sk-ecdsa-sha2-nistp256-cert-v01@openssh.com,rsa-sha2-512-cert-v01@openssh.com,rsa-sha2-256-cert-v01@openssh.com,ssh-rsa-cert-v01@openssh.com,sk-ssh-ed25519@openssh.com,sk-ecdsa-sha2-nistp256@openssh.com,ssh-ed25519,ecdsa-sha2-nistp521,ecdsa-sha2-nistp384,ecdsa-sha2-nistp256,rsa-sha2-512,rsa-sha2-256,ssh-rsa>
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey
debug1: Next authentication method: publickey
debug1: Offering public key: /Users/user001/.ssh/id_ed25519 ED25519 SHA256:d1IU7r1+0qOrFCNtmhBIlpUs7UvUOqQx0hqIumMQa6M agent
debug1: Server accepts key: /Users/user001/.ssh/id_ed25519 ED25519 SHA256:d1IU7r1+0qOrFCNtmhBIlpUs7UvUOqQx0hqIumMQa6M agent
Authenticated to github.com ([192.30.255.112]:22) using "publickey".
debug1: channel 0: new [client-session]
debug1: Entering interactive session.
debug1: pledge: filesystem
debug1: client_input_global_request: rtype hostkeys-00@openssh.com want_reply 0
debug1: client_input_hostkeys: searching /Users/user001/.ssh/known_hosts for github.com / (none)
debug1: client_input_hostkeys: searching /Users/user001/.ssh/known_hosts2 for github.com / (none)
debug1: client_input_hostkeys: hostkeys file /Users/user001/.ssh/known_hosts2 does not exist
debug1: client_input_hostkeys: no new or deprecated keys from server
debug1: Sending environment.
debug1: channel 0: setting env LANG = "en_US.UTF-8"
debug1: client_input_channel_req: channel 0 rtype exit-status reply 0
Hi 100stacks! You've successfully authenticated, but GitHub does not provide shell access.
debug1: channel 0: free: client-session, nchannels 1
Transferred: sent 2020, received 2576 bytes, in 0.4 seconds
Bytes per second: sent 5584.2, received 7121.3
debug1: Exit status 1
```

- Notice about mid-way in the above output the ssh handshake, and GitHub accepting my `public key`.

```zsh
debug1: SSH2_MSG_SERVICE_ACCEPT received
debug1: Authentications that can continue: publickey
debug1: Next authentication method: publickey
debug1: Offering public key: /Users/user001/.ssh/id_ed25519 ED25519 SHA256:d1IU7r1+0qOrFCNtmhBIlpUs7UvUOqQx0hqIumMQa6M agent
debug1: Server accepts key: /Users/user001/.ssh/id_ed25519 ED25519 SHA256:d1IU7r1+0qOrFCNtmhBIlpUs7UvUOqQx0hqIumMQa6M agent
Authenticated to github.com ([192.30.255.112]:22) using "publickey".
debug1: channel 0: new [client-session]
debug1: Entering interactive session.
debug1: pledge: filesystem
```

```zsh
git config --global commit.gpgsign true
```

```zsh
git config --global --list
user.email=100stacks@users.noreply.github.com
commit.gpgsign=true
```
