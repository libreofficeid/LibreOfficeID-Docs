# Build & Install

### Build Extension

To build LO-TC, just follow this steps:

```bash
# clone repository
git clone https://github.com/libreofficeid/LO-TC-GUI.git

# enter to clone directory 
cd LO-TC-GUI

# build extension
make zip
```

we have special command `make all` to everyone who wanna help us to develop this extension. This command used if you have make some update to python code, and wanna to show the update directly on your LibreOffice without re-install extension via Extension Manager. Just run `make all` then restart the LibreOffice.

{% hint style="info" %}
Some operating system doesn't provide **python3-uno** package/library which is needed to run LOTC. Please make sure that this library already installed on your system before running LOTC.
{% endhint %}

\`\`

### Extension Installation

Just like other extension, you only need to import this extension via menu: Tools -&gt; Extension Manager, then add extension. LibreOffice should restart after new extension installation.

For your information, at the first run, LO-TC will ask you for root permission to setup local environment.

Here is special note for Slatpak, Snap, and Windows user.

**Only for flatpak user**,   
please run [**lotc-flatpak-first-run.sh**](https://raw.githubusercontent.com/libreofficeid/LO-TC-GUI/master/lotc-flatpak-first-run.sh) first. LibreOffice will opened, then open menu: Tools -&gt; Extension Manager -&gt; add extension.

**Only for Windows user**  
After installing the extension and running it at the first time, you will be asked for many times User Account Control \(UAC\) for Administrator Privileges to do some modifications in LibreOffice Installation Directory. UAC will be prompted again when activating your desired theme.

**Only for Snap user**  
After installing the extension and running it at the first time, you will be noticed that you have to run additional step to make this extension works. While running desired script, it will ask for sudo password to perform some modifications of your LibreOffice's Snap installation. After that, you should reboot your PC to apply this modifications. Then, you can normally run LibreOffice Snap version.

