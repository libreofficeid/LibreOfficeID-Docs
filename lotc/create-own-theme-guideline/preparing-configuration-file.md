# Preparing Configuration File

After you have prepared the image assets, now let's prepare the configuration files. Here are some configuration files that you must prepare:

1. **persona\_list.txt**  


   **persona\_list.txt** is a configuration file to control how our theme will be displayed. The file contains information as follows: 

   * Theme Directory Name 
   * Theme Name \(will appear as a tooltip\) 
   * Location of the preview file 
   * Location of the header file 
   * Footer file location 
   * Backgrond and foreground colors

   The following is an example of the format of writing the information above \(for example a theme created called Rainbow\).

   ```text
   rainbow;Rainbow;rainbow/preview.png;rainbow/header.png;rainbow/footer.png;;#ffffff;#000000
   ```

2. **sofficerc**   
   ****sofficerc is a file that will control how splash will be displayed. The following is the contents of the sofficerc file and some explanations.



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

   To customize the look you only need to edit the following parameters;  
  
   **A. Logo**   
   Parameters to determine whether the splash is displayed or not  


   **B. NativeProgress**   
   Displays native or custom progressbar

  
   **C. ProgressBarColor**   
   ProgressFrameColor determines the frame color on the progressbar, this parameter uses the RGB color value  


   **D. ProgressPosition**   
   Determine the location of the progressbar, this parameter uses the X and Y coordinate values  
  
   **E. ProgressSize**   
   Determining the size of the progressbar, this parameter uses the width and height values in pixels.

