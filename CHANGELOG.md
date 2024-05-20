# ChangeLog

## [0.2.2] - 2024-05-19

### Added

- New function machineInfo in 00-misc.sh to get version codename.
- New function switchRelease in 10-packages.sh which asks user if they want to switch update trains on Debian.

### Fixed

- Was trying to enable sshd.service in 10-packages.sh function detectPackagesInstalled and changed it to read "ssh.service" to prevent errors if the symbolic link exists between ssh.service and sshd.service.
- Fixed function sshAuthorizedKeys in 30-ssh.sh when asking a user to input SSH keys, no if statement existed.

## [0.2.1] - 2024-05-19

### Fixed

- Fixed the wrong function being called in 30-ssh.sh (Was calling ssh_key_setup instead of sshKeySetup)
- Added missing "fi" statement in 30-ssh.sh line 43
- Added warning to not run the script as root.

## [0.2] - 2024-05-14

### Added

- Added an option tree (function main) to the main script so you can select which functions you'd like to run.
- nvimEnsureConfig function in 00-misc.sh to detect if the required dependencies for a nakouchdoge/nvim clone are present.
- nvimEnsureConfig function added to main script. 
- Choice to install ufw if it's not installed in detectUfw function in 40-firewall.sh 

### Changed

- detectUfw function in 40-firewall.sh changed from grep command to [ -f "/usr/sbin/ufw" ] for easier readability. 
- enableUfw function in 40-firewall.sh changed from grep command to [ -f "/usr/sbin/ufw" ] for easier readability. 
- End of script message no longer tells you to log out and log back in, because this may not always be the case.

### Fixed

- bashPrompt function in 20-bash.sh lines 20 and 30 were writing to .bashrc, now writes to .bash_prompt. 

## [0.1] - 2024-05-13

_First release_