
This is a repo where we store all of our scientific (computer science) knowledge.
We also write on experiments and issues we've had.
It is made to be read in Obsidian. Feel free to clone and to use it !

### Sync on Mobile

1) Download Termux on [Play Store](https://play.google.com/store/apps/details?id=com.termux&hl=fr&gl=US)  or [Softonic](https://termux.fr.softonic.com/android)
2) ```pkg update && pkg upgrade```
3) ```termux-setup-storage```
4) ```pkg install git```
5) `git clone`

This is enough if you only want to read the content. Then use the obsidian git plugin to pull

#### Push through http
1) ```pkg install gh```
2) ```gh auth login```
3) setup github token (not recommended)

#### Push through ssh
1) `ssh-keygen -t ed25519 -C "your_email@example.com"`
2) Ask me to add you public key on github

Note : with this method you will only be able to push on termux but it's way safer than using a github token.


### Obsidian tricks

Split view open : ctrl+click on the read/write btn

[supported code color](https://prismjs.com/#supported-languages)

### Obsidian shortcuts

```c
<Ctrl+e> toggle editing mode
<Ctrl+Maj+F> Find file
<Ctrl+f> Find in file
<Ctrl+h> Replace in file
# Personal custom shortcuts
<Ctrl+Maj+E> Open file explorer
<Ctrl+t> toggle left sidebar
<Alt+c> commit
<Alt+p> push
<Alt+l> pull
```

### Resize images 

Use the `image.css` file.

```markdown
<span class="rightimg"><span class="smallimg">
![[myImage.jpg]]
</span></span>
```

The classes are : 

`.leftimg`
`.centerimg`
`.rightimg`

`.tinyimg`
`.smallimg`
`.mediumimg`
`.largeimg`


### Responsive design

```markdown
<span class="mobile">THIS TEXT IS ONLY DISPLAYED ON MOBILE</span>
<span class="desktop">THIS TEXT IS ONLY DISPLAYED ON DESKTOP</span>
```

<span class="mobile">THIS TEXT IS ONLY DISPLAYED ON MOBILE</span>
<span class="desktop">THIS TEXT IS ONLY DISPLAYED ON DESKTOP</span>


