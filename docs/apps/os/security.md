# Security and safety

A development machine should be secured against threats as well as any other machine (or even especially a research
 machine). Therefore, depending on your operating system, you should consider:

- choosing a known, secure Linux distribution with secure system settings
- installing a virus scanner/protection (if you are running Microsoft Windows)
- installing and configuring a firewall
- setup disk encryption on your workstations


## Linux distribution

Chose a known and recognized Linux distribution. ÉTS supports Linux Ubuntu. Choosing Ubuntu is ususally the best 
choice you can do when being in the lab.

## Firewall

### macOS
To turn on the built-in firewall on macOS:

1. Choose Apple menu () > System Preferences, then click Security & Privacy.
2. Click the Firewall tab.
3. Click the Lock button, then enter an administrator name and password.
4. Click Turn On Firewall.


### Ubuntu
To turn on firewall on Ubuntu:

1. Install the firewall-config package. 
2. Ensure the firewalld service is up and running.
3. Configure interface with the firewall GUI app.

 
## Disk encryption

You will have in your possession a lot of medical images. While these images have been anonymized, it's still personal 
data from patients.

It is strongly recommended you activate disk encryption on your workstations, especially on a mobile computer. If you 
travel a lot and take your notebook with you (including all your source codes), you might consider travelling with disk
encryption enabled.

### macOS
To activate disk encryption on macOS:

1. Choose Apple menu () > System Preferences, then click Security & Privacy.
2. Click the FileVault tab.
3. Click the lock button, then enter an administrator name and password.
4. Click Turn On FileVault.

See [official Apple support page](https://support.apple.com/en-us/HT204837) and 
[About encrypted storage on Mac](https://support.apple.com/en-us/HT208344) for more details. 


### Ubuntu
On Ubuntu, disk encryption should be set upon installing the operating system.


### Backup

Backing up your data is always the best thing you can do to preserve your data integrity in case of disaster. Since 
these backups can also contain medical images, it is strongly recommended to activate disk encryption on the media
you are backing up your data. 

On macOS, make sure you have an encrypted Time Machine Backup.