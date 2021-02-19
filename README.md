# GPG and git guide

## Introduction
This guide mainly focuses on using GPG together with git and services such as GitHub and GitLab from the perspective of a developer. It is therefore fairly practical and does not cover the various security concepts that is used by GPG.

The main benefits of using GPG as a developer/git user:
- I can certify that I have made a certain change by signing my git commits.
- I can authenticate myself towards services using SSH.

### YubiKeys and GPG
The keys generated by this guide can be transferred and used on YubiKeys. See drduh's guide on that topic: https://github.com/drduh/YubiKey-Guide.

From the guide:
> Keys stored on YubiKey are non-exportable (as opposed to file-based keys that are stored on disk) and are convenient for everyday use. Instead of having to remember and enter passphrases to unlock SSH/GPG keys, YubiKey needs only a physical touch after being unlocked with a PIN. All signing and encryption operations happen on the card, rather than in OS memory.

### Scope and security
This will mainly be aimed at macOS users since that is what I use myself. It is also written to be as basic as possible to get the keys generated. Depending on the use case more secure ways should probably be used when generating and handling the keys (such as increasing randomness, generating and storing the keys offline etc).

## GPG keys
### Requirements
Homebrew (https://brew.sh) is used to install the packages.
```
$ brew install gnupg
```

### Generating keys
#### Master key
The master key will only be used for issuing sub-keys and signing other keys.
```
$ gpg --expert --full-generate-key
```
Choose the following alternatives:
- `Please select what kind of key you want`: `8`
- `Possible actions for a RSA key`: `E`, `S` then `Q`
- `What keysize do you want?`: `4096`
- `Key is valid for?`: `0`
- `Is this correct?`: `y`
- Enter your name and email address when prompted
- Comment is optional
- Enter a passphrase
  - It is important that this is remembered or stored in a password manager


#### Signing key
Signing key.

#### Encryption key
Encryption key.

#### Authentication key
Authentication key.

### Master key backup and cleanup
Backup and remove master key

## Use cases
### Git signing
Git configuration for signing commits manually or automatically.

### SSH
Public key for SSH authentication.

### GitHub keys
Upload SSH and GPG public keys to GitHub.

### GitLab keys
Upload SSH and GPG public keys to GitLab.

## More reading
https://docs.github.com/en/github/authenticating-to-github/managing-commit-signature-verification

## TODO
- Clean up links
