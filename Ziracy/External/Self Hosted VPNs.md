**Note** - The best OS to use for this is Ubuntu

---

**Step 1.** For this you will need a linux server, I use Ubuntu 16.xx or 18.xx.

**Step 2.** First, You must connect to your server with PuTTY or MobaXTerm or whichever tool you prefer to use, I use MRemoteNG because it's FOSS.

**Step 3.** Once connected to your server, run this command: the “curl” dependency is needed for this, to install it do "apt install curl"

`curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh && chmod +x openvpn-install.sh`

**Step 4.** Now you have to run the openvpn installer with this `./openvpn-install.sh`

**Step 5.** During the setup, it will ask some questions about how it should install. You can just press enter and it will use default settings.

**Step 6.** It will ask for what you want to name the "client", name it anything you want. Then, Once done it should generate the open vpn configuration.

**Step 7.** To see if the file was made run `ls` in the command line. You should see a file made with that name.

**Step 8.** Then you can just copy the configuration over to your computer with WinSCP or MobaXTerm and then use it with openvpn.

---

You can find cheap servers **[here](https://billing.virmach.com/aff.php?aff=4109&url=billing.virmach.com/cart.php?gid=18).**

More Self-Hosts can be found **[here](https://github.com/Igglybuff/awesome-piracy#self-hosted-vpns).**