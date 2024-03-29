# apo-ssh

## What

This script makes Aporeto PAM SSH easy. It will automatically create a keypair if it does not already exist. The first time you call it, it will get a token using your specified identity provider. Then it will get a certificate using the token. It will cache the certificate and token locally. The next time you run it it will check the validity of the certificate and if its good will use it. If its expired it will get a new certificate and cache it locally. If the token is expired it will try to get a new token from your identity provider.

## Installation

Put the script on your host. Make sure the execution bit is set with chmod +x this_script. Then add an alias to your profile to call this script instead of ssh directly. Be sure to configure it.

1. Install the apoctl cli 

```
      sudo curl -o /usr/local/bin/apoctl \
        https://download.aporeto.com/apoctl/darwin/apoctl && \
      sudo chmod 755 /usr/local/bin/apoctl
```

2. Copy the script `apo-ssh` to the home directory and change the permission to +x

4. The default configuration is PAM_AUTH_PROVIDER is Auth0 and APOCTL_NAMESPACE is /somos/dev which is in the script. 

## Configuration
In case you have enforcers in a different namespace change the APOCTL_NAMEPSACE
In case you a different auth provider change the PAM_AUTH_PROVIDER

