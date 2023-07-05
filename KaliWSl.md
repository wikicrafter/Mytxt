Inside of Kali WSL: kex --win -s

On Window's command prompt: wsl -d kali-linux kex --win -s


To start Win-KeX in Enhanced Session Mode with sound support and ARM workaround, run either:

Inside of Kali WSL: kex --esm --ip -s

On Window's command prompt: wsl -d kali-linux kex --esm --ip -s

To start Win-KeX in Seamless mode with sound support, run, run either:

Inside of Kali WSL: kex --sl -s

On Window's command prompt: wsl -d kali-linux kex --sl -s

For more information, ask for help via:

kex --help

man kex

Start Root Session

Start Win-KeX as root in window mode via: sudo kex --esm

You will be prompted to set an ESM server password during first launch. This is the password for the kali root user.

The password can be changed later via: sudo kex --esm --passwd

This will start the Win-KeX server as root and launch the Win-KeX client in full screen mode. 
