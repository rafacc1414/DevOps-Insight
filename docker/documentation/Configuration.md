# Configuration of Docker Engine in Ubuntu

## Work without beeing root

Follow the page: [How to fix docker: Got permission denied issue](https://stackoverflow.com/questions/48957195/).

There we can see all the groups in our OS.

```bash
cat /etc/group
```

After docker installation, by default, the group ```docker:x:998:``` is created.

So, if we want to work with docker without being root, just add the user to this group. In my case:

```bash
sudo usermod -aG docker rafacc
```

Run in the terminal: 

```bash
newgrp docker
```

Then it must work.

