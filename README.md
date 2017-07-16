# adapTor
A project focused on making it easier to integrate the Tor Network into any application

### Why Does This Exist?
Tor is an awesome tool to allow you to communicate with the internet privately. There are a ton of reasons why you may want to use it. The issue, is that if you wanted to use Tor in an application you're developing you need to have your users either run Tor themselves, or automate the installation for them. Because of this, it makes bundling Tor with your application difficult and a barrier to entry. adapTor hopes to change this.

### What Does adapTor Do?
The goal of the adapTor project is to make it much easier to bundle Tor alongside a standard application. No more SOCKS proxies. No more changing your network settings. In theory, there will be a simple API to call a TorSocket which will act as a standard socket. Simply compile your application with the Tor libraries and you'll be all set. I have taken the Tor source code (found [here](https://www.torproject.org/download/download.html.en), I'm using version 0.3.0.9) and modified it for this project.

### Project Goals
1. Remove the need for the SOCKS proxy
2. Create an API to interact directly with the Tor Daemon (TorSocket sock = new TorSocket();)
3. Make it possible to bundle the Tor Daemon directly into an application
4. Remove the bloat of the Tor Daemon, removing extraneous features typically used by relays
5. Ensure that even with significant modification, we can still use all the features of Tor such as Pluggable Transports

### How Do I Compile adapTor?
You will compile adapTor the same way you would traditionally compile Tor. The only caveat is that you need to swap the source files of Tor with the adapTor source files. Simply go to the 'src' folder of your Tor code, then go to the 'or' directory. Simply drag and drop the adapTor code and say "Replace All". Do NOT swap the 'or' folder with the adapTor 'or' folder. There are certain files (fallback_dirs.inc, include.am, Makefile.nmake) that cannot be over written or it will mess up your ability to compile.

### Where Is The Project In Terms Of Completion?
Just getting off the ground. The Tor Daemon is a very complex piece of software with many features we don't need. As a result there will need to be some research and familiarization. Some early progress has been the ability to identify the parts of code where the target IP as well as the payload (packet data) location. In addition, we are able to recieve responses. This is a side project for me, if you want to assist I am open to it!
