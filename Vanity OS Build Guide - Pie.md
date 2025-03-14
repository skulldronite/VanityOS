**Build Guide for Vanity OS Flavour - Vanity S**

This is going to be a guide on how to build the Legacy flavour, of Vanity OS. You will need all the files within the "**Download List**". This guide is similar to the Vanity OS Legacy guide, with a couple of changes to accomodate Android Pie's Samsung.

**Step 1: Downloading Pie firmwares:** <br>
1. We'll need to get our stock **Pie** Samsung firmware, that we'll use as a base to work on. Head over to https://samfw.com/ , and type in your model no. to find the firmware you need. <br>
2. Target these **CSCs** when given the choice, as they offer the most features/compatibility:<br>
- BTU <br>
- XSA <br>
- XSG <br>
- XFA <br>
- KOO <br>
Download only **one** of the CSCs, and follow this priority of availability in CSCs, in this order. For example, if BTU is not available, then get XSA. If XSA is not available, then get XSG and so forth. Hit the "**"Download in browser"**, and wait for it to download. <br>
3. Also ensure that you have extracted the "**Vanity OS - Dev Kit**" zip file that you downloaded, since you'll need a lot of the files within this.

**Step 2: Extracting and decrypting the firmware:** <br>
1. Now that we have our firmwares, store them in a new folder. Label the folder as "Classy (insert model of device)", and place the **Classy Kitchen Executable**, in this folder.
2. Double click the Classy Kitchen executable, and wait for it to load. Once it loads, click "**Create New Project**. <br>
3. Once you do this, it should open a new prompt, asking where you want to pull the firmware source from. Click on "**From PC (Browse for one)**", and then select the firmware zip file that you downloaded. <br>
4. It will now ask for a project name. Name it **"Vanity OS 1.0 - (insert model number) - (insert today's date)"**. After this, it will start extracting. <br>
5. It will finally ask to input a name for the **flashing of the ROM**. Just input whatever random name you want, as we will have to rebuild the installer script later.
   
**Step 3: Running the first De-skin scripts:** <br>
1. Once the firmware extracts, click on the **ROM Utils** button, and click on **Debloat/Bloat ROM**. <br>
2. Once you click on this, the windows explorer menu will open. Select the **Pie Vanity MDB** file, which is stored with the "**Vanity OS - Dev Kit**" folder that you extracted earlier. The kitchen will now begin removing and de-skinning the firmware. Once this is done, we can begin dekinning the firmware further by editing both the feature files, as well as the camera_feature files.
   
**Step 4: De-skinning Floating_feature:** <br>
1. For this section, you will need to dive into the system files, to begin removing features, and any other un-necessary files. First go into the **Classy Kitchen** folder, and into the folder called **Project**. Once there, go into the folder called **system**, and then the **etc** folder.<br>
2. Within here, you will now see a file called **floating_feature**. Open this file on you're preferred IDE or just open it in plain old Notepad. <br>
**Before you continue, please ensure that you make a backup of this file, as if you make a change that you didn't intend, or ever need to reference it again, you'll have to rextract the entire firmware to get this singular file, so a backup of this file is HIGHLY recommended**.<br>
3. Now keep the original factory **floating_feature** file in splitscreen on the left, and naviagate to the **Vanity OS - Dev Kit** folder, and open the file called "**PP - floating_feature.xml**. Put this file in splitscreen and compare the two.<br>
4. Looking at the two files, you will notice that factory floating_feature file, has significantly more lines in comparison to the PP file. What you want to do, it to start **removing** lines that are in the factory file, but are not in the OP file. **Please ensure you are careful when deleting these lines, since making a mistake such as leaving a bracket unclosed, or removing the wrong file, will result in the ROM bootlooping or unintended feature breaks. I have extensively tested the removal of the lines that I have selected, so I can verify that these do not cause issues. If you want to remove more lines, then feel free to experiment, but DO NOT RELEASE THE BUILD WITHOUT TESTING.** <br>
5. Once you have removed all the lines, head to the particular line: <br>
**<SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>Galaxy Tab S2</SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>**. <br>
Now your line may look a little different, depending on the model that you are building for, but that doesn't matter. Over here, edit the name to say "Vanity OS (insert device name here)". A finished version, looks like this: <br>
**<SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>Vanity OS 1.0 - Tab S2</SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>**. <br>
7. After you have done this, save the new factory file, and you can move on to the next step.

**Step 5: Cameradata:** <br>
**Note: Since this section does not have a direct file to compare too, if you are uncomfortable doing this without a reference point, you may skip this section.** <br>
1. Now that we finished the floating_feature file de-skin, we can now move on to the next component, which is the **cameradata**. Go back one directory from inside the **etc** folder, and you will see the entire system again. You'll see a folder called **cameradata**. Go inside it, and open the **camera_feature** file within it. Again you may use any IDE or something as simple as Notepad will still work.<br>
2. Once within it, look at the code within. Under the **Modes** section, delete any modes that are un-necessary such as **Panorama, Continuous_Shot, Food, & 360**. <br> **Note: Please be just as careful here, as removing the wrong mode, or leaving an unfinished bracket will cause the camera app to always crashing on launch.** <br>
3. Once this is done, save the file, and we are almost done! <br>

**Step 6: Build.prop editing:** <br>
1. In this section, we're gonna be editing our build.prop to sign our work! So to do this, just go back one directory from the **cameradata** folder, and you can see all the system files again. At the bottom, there should be a file called **build.prop**. Open it in an IDE or Notepad.
2. Once you open the file, you should see almost immediately on top, a line called: <br>
**ro.build.display.id:**. Along with this, you'll see a line stating the build number, and this is the line we'll be editing.<br>
3. Edit this line so that the model number and its CSC is at the end, and before that it shows the name of the ROM we're making. An example of a finished line for Vanity OS is: <br>
**ro.build.display.id=VanityOS.1.0-T815N0KOU3CTD1** <br>
Notice, that at the end is the full build ID of the stock firmware, and at the start is name of the ROM we have built. <br>
4. Once this is done, save the file, and we are now done with the **de-skinning** process of building a ROM! <br>

**Step 7: Adding back any cut content:** <br>
1. Now that we have completed removing features and application, let's now start adding any required replacements. Stay in the main system directory you're on, and put this folder on your left splitscreen. Now open the **Vanity OS - Dev Kit** folder, and navigate to the **Oreo & Pie Module** folder. <br>
2. Within this folder, you'll now see multiple files, with different names. We'll only need two files from this folder. Copy the **Files** folder from the **Oreo & Pie Module** to the app folder in the main directory of your system. Along with this, copy the **wallpaper** folder to the main directory of your system. This will setup a default Vanity OS Legacy Wallpaper, for when the user first boots in. If you wanna add your own custom wallpaper, head into the wallpaper folder, and replace the pictures in there, with the same filename. **It has to be a 1:1 file name, or the system will not acknowledge it.**. <br>
3. Go back to the main folder of the **Oreo & Pie Module**, and put the two files, NotoColorEmoji.ttf & SamsungColorEmoji.ttf into your clipboard. Now navigate to your system's main directory, and into the "**fonts**" folder. Paste the two files within there.
And we're finally done building our Vanity OS ROM! <br>

**Step 8: Rebuilding the META-INF and Compiling ROM**<br>
1. We're on the final few steps now. Close all your folders, and go back to **Classy Kitchen**. Once Classy Kitchen is open, click on the "**META-INF Utils** button, and then click on "**Rebuild META-INF installer:**". Once you click this, a prompt will appear asking what name you'd like when the ROM is being flashed. Input this name, in this format: <br>
**Vanity OS (version number) - (insert model no.) - (insert today's day)** <br>
So a finished name, would look like this: <br>
**Vanity OS 1.0 - T815 - 5/03/2025** <br>
Once you have given the name, click the confirm button, and wait for the kitchen to rebuild your **META-INF** file. <br>
2. Once the **META-INF** file is created, click on the "**Project Utils**" button, and click on the "**Build ZIP ROM (for recovery)**" button. Once this is done, the kitchen will ask whether you'd like to **Zip Align** the ROM before compilation. Click **Yes**. <br>
3. After the kitchen finishes zip aligning, another prompt will appear asking what would you like to name the zip file. **Input the name Build1**.
4. Once the ROM finishes compiling, go into the **Classy Kitchen Folder**, and go-to the "**Output**" folder, and you will now see your finished ROM! Just rename the zip to this format: <br>
**Vanity OS (insert version number) - (insert model number) - (insert current date)** <br>
A finished zip file name should look like this: <br>
**Vanity OS 1.0 - T815 - 5-03-2025.zip** <br>
And with that, **CONGRAGULATIONS**! Your ROM build is officially complete! Upload this zip file to whatever file sharing host server you want, make your **XDA thread**, and post it!
