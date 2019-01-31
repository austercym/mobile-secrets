# Secrets used in our mobile apps

This repo uses https://github.com/StackExchange/blackbox to encrypt/decrypt secrets. Blackbox code is embedded in the repo so you don't have to install it separately, just follow the instructions.

## How to get access to the secrets

1. Install GPG in your computer if you don't have it
2. Create a GPG key if you don't already have one
```gpg --gen-key```
3. Send your public key ```gpg --armor  --export <your certificate email address>``` to one of the admins listed at https://github.com/OrwellGroup/mobile-secrets/blob/master/.blackbox/blackbox-admins.txt
4. Ask them to add you as an admin

## How to decrypt the secrets

1. You need to be an admin, listed at https://github.com/OrwellGroup/mobile-secrets/blob/master/.blackbox/blackbox-admins.txt . Follow "How to get access to the secrets" if you are not
2. Type ```./blackbox/bin/blackbox_decrypt_all_files```
3. Now all the secrets are decrypted
4. After you used the secrets you should ```./blackbox/bin/blackbox_shred_all_files``` to remove them from your computer

## How to add secrets

1. You need to be an admin, listed at https://github.com/OrwellGroup/mobile-secrets/blob/master/.blackbox/blackbox-admins.txt . Follow "How to get access to the secrets" if you are not
2. Create secrets in the ```secrets``` folder. It's a good practice to add them in a sub folder like ```secrets/ios-certs/```
3. Register the secret files with ```./blackbox/bin/blackbox_register_new_file <path file>```
4. Update all file with ```./blackbox/bin/blackbox_update_all_files```
5. Commit and push the repo

## How to add an admin

1. You need to be an admin, listed at https://github.com/OrwellGroup/mobile-secrets/blob/master/.blackbox/blackbox-admins.txt . Follow "How to get access to the secrets" if you are not
2. Ask the new admin to send you their GPG public key
3. Add the new admin ```./blackbox/bin/blackbox_addadmin <gpg public key of the new admin>```
4. Update all file with ```./blackbox/bin/blackbox_update_all_files```
5. Commit and push the repo





