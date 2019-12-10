# Create a Custom Theme



Please follow this steps to create a custom LibreOffice theme.

#### Understanding Directory Themes Hierarchy

The LO-TC use special directory hierarchy to make it easier for anyone who wants to create a custom theme and install it using LO-TC. Save and place each assets that will be created in the **themes** directory. LO-TC will automatically read the list of themes contained in the directory, we call them preinstalled themes.

please pay attention to the following directory hierarchy to help you find out where the assets are stored in the next steps.

```bash
themes
└── your-theme
    ├── program
    │   ├── intro.png
    │   └── sofficerc
    ├── screenshot.png
    └── share
        └── gallery
            └── personas
                ├── your-theme
                │   ├── footer.png
                │   ├── header.png
                │   └── preview.png
                └── personas_list.txt
```

\[UPDATE\] We have provided additional tools to help you create a full and fast theme folder. Just run the command:

```bash
$ bash theme-creator.sh
```

then enter the name of the theme you want. Automatically the LO-TC will create a theme directory according to the name you entered under the `themes` folder.

#### Preparing Image Assets

The pictures that must be prepared to make this theme include:

1. Splash Splash is the image that appears at the first time when you run LibreOffice. Actually there is no standard size for this splash image, but we recommend using the size that is also used by LibreOffice which is 661x169 pixels. You can make a splash using the template that we have provided. [Download here](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/intro.svg)
2. Header The header is an image that appears at the top of the LibreOffice program, precisely in the LibreOffice menu area. We use the header size from the standard image size assets on Firefox persona themes. We strongly recommend that the design created for this header take advantage of the upper right corner area. The technical reason is because this area is the most save area and does not interfere with the visibility of the icons on the menu. We have prepared a header template that is ready to be modified. [Download Here](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/header.svg)
3. Footer Footer is an image that will appear in the area under the LibreOffice program. Basically this footer will be hidden automatically if there is no menu open at the bottom/footer of LibreOffice. The safe area for this footer is on the right side, please use the template that we have provided to help you create a footer. [Download Here](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/footer.svg)
4. Preview Preview is an image that will be displayed in the `tool` menu -&gt; `Options` -&gt; `Personalization`. This preview becomes the identity of your theme. The safe area for this preview image is in the middle of the area. Please download the preview template that we have provided. [Download Here](https://github.com/libreofficeid/LibreOfficeID-Docs/tree/853bc61dbe5602735a5fc6e5321c981647286997/LibreOffice%20Theme/template/preview.svg)
5. Screenshot \(optional\) Help other users recognize your theme by providing screenshots when your theme is successfully installed.

#### Create Configuration Files

After you have set up image assets, let's now prepare configuration files. Here are some configuration files that we will prepare:

1. Sofficerc `sofficerc` is a file that will set how the splash will be displayed. Here is the contents of the sofficerc file followed by simple explanations.

   ```bash
   [Bootstrap]
   CrashDirectory=${$BRAND_BASE_DIR/program/bootstraprc:UserInstallation}/crash
   HideEula=1
   Logo=1
   NativeProgress=false
   ProgressBarColor=0,0,0
   ProgressFrameColor=102,102,102
   ProgressPosition=35,153
   ProgressSize=444,8
   ProgressTextBaseline=145
   ProgressTextColor=0,0,0
   SecureUserConfig=true
   SecureUserConfigCompress=true
   SecureUserConfigExtensions=true
   SecureUserConfigMode=1
   SecureUserConfigNumCopies=2
   URE_BOOTSTRAP=${ORIGIN}/fundamentalrc
   ```

   to customize splash display you only need to edit parameters, `logo`,`NativeProgress`, `ProgressBarColor`,`ProgressFrameColor`, `ProgressPosition`, and `ProgressSize`

   * Logo -- parameter to determine whether the splash is displayed or not
   * NativeProgress -- Displays _progressbar_ native or custom
   * ProgressBarColor -- Specifies the color _progressbar_, this parameter uses RGB color values
   * ProgressFrameColor -- Specifies the color of the frame at _progressbar_, this parameter uses an RGB color value
   * ProgressPosition -- Determine location _progressbar_, this parameter uses X and Y coordinate values
   * ProgressSize -- Specifies the size of _progressba_, this parameter uses a value of width and height in pixels

2. persona\_list.txt `persona_list.txt` is a configuration file to set how our theme will be displayed. The file contains the following information:

   * Name of Theme Directory
   * Theme Name \(also will appear as a tooltip\)
   * Location of preview file
   * Location of header file
   * Location of the footer file
   * Backgrond and foreground colors

   Here is an example of the format for writing the information above \(for example, a theme named _**rainbow**_\).

   ```bash
   rainbow;Rainbow;rainbow/preview.png;rainbow/header.png;rainbow/footer.png;;#ffffff;#000000
   ```

After all the assets and configuration files are ready, please run the LO-TC, if the steps are done correctly, your theme should appear as a list of ready-to-use themes.

