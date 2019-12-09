# apo-ssh

## What

This script makes Aporeto PAM SSH easy. It will automatically create a keypair if it does not already exist. The first time you call it, it will get a token using your specified identity provider. Then it will get a certificate using the token. It will cache the certificate and token locally. The next time you run it it will check the validity of the certificate and if its good will use it. If its expired it will get a new certificate and cache it locally. If the token is expired it will try to get a new token from your identity provider.

## Installation

Put the script on your host. Make sure the execution bit is set with chmod +x this_script. Then add an alias to your profile to call this script instead of ssh directly. Be sure to configure it.

## Configuration
You will need to set the required vars PAM_AUTH_PROVIDER and APOCTL_NAMESPACE. You may optionally set the var APOCTL_API
