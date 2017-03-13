Bash script for 'harderning' linux-based servers. Written in 2017 by Mark Southworth. This script is not supported nor will I take any responsibility for any issues, problems and/or errors that may occur on your system due to running the configuration script. If you are unsure on the impact this script may have on your host, please test on a VM/backup anything imperative. 

Owner Contact:
Email - Mark.southworth98@gmail.com
Linkedin - https://www.linkedin.com/in/mark-southworth-144a02105/
Git - https://github.com/MadNoob98

Below is a more detailed explanation of what each part of the script does, how to disable certain features and the potential impacts they could have on your system.

1) Installing/Configuring NTP.
The first step installs Network Time Protocol (NTP). In a coporate environment, it is often important to have NTP installed for compliance reasons. NTP makes sure the time on your system is 100% accurate, this can help with logging and things like cron jobs etc. 

NTP could have impacts on the following, so please double check them after the script has ran;
- cronjobs (due to the time change (if any) they could run out of sync)
- Your host could become out of sync with backups (if ran at a certain time)

The package is installed using Yum (Yellowdog update manager).

2) Installing/configuring Advanced Intrusion Detection.
Secondly comes the installation of Advanced Intrustion Detection (AIDE). AIDE can be used to monitor file changes, including; permissions, ownership, timestamp and content changes. 

Again, this package is installed using yum.

AIDE should not have any adverse impacts on your system, so far I haven't noticed anything out of the ordinary occuring after installation. If you do notice something please get in touch and i'll update the readme.

3) Disable zeroconf networking.
Step three involves disabling the usage of 'zeroconf' networking. Disabling zeroconf networking takes away 'predictable' IP addresses with are automatically assigned when DHCP fails/your host cannot reach DHCP.

This step does not install a package, it only changes the network configuration. If you're network configuration relies on zeroconf networking then please remove/hash out this step.

4) Ensure ryslog is enabled
Step four is checking rsyslog is installed and enabled. This is an imprative step within the server hardening script.  
