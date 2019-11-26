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

### Extension Installation

Just like other extension, you only need to import this extension via menu: Tools -&gt; Extension Manager, then add extension. LibreOffice should restart after new extension installation.

For your information, at the first run, LO-TC will ask you for root permission to setup local environment.

\[Update\] Only for flatpak user, please run **lotc-flatpak-first-run.sh** first. LibreOffice will opened, then open menu: Tools -&gt; Extension Manager -&gt; add extension.

