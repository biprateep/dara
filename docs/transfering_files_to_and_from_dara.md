# Transfering files using a linux terminal 
rsync (remote synchronization) in linux can be used to efficienty sync files and directories between two hosts or machines. This is better than other commands that just copy files because rsync only copies differences (so you can keep things up to date without copying things that are the same in both directories). It is simple to use:

```bash
rsync local-file user@remote-host:remote-file
```

For example, to copy something (something.py) from the "/Desktop/research/codes/" directory on my computer to my dara home, I can open a terminal (on my machine) and run the command

```bash
rsync -a ~/Desktop/research/codes/something.pi ask126@dara.phyast.pitt.edu:/home/ask126/
```
This will first ssh to dara so it asks for a password. "ask126" is my username so replace it with yours.
The "-a" is to activate archine mode.

To copy all the files in the directory "something" to your home directory on dara, you can do something like (note the forward slashes /, they matter)

```bash
rsync -a ~/Desktop/research/codes/something/ ask126@dara.phyast.pitt.edu:/home/ask126/
```
