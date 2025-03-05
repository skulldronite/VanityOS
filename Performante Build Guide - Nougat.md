#**Build Guide for Vanity OS Flavour - Performante**

This is going to be a guide on how to build the Performante flavour, of Vanity OS. You will need all the files within the "**Download List**".

**Step 1: Downloading Nougat firmwares:** <br>
1. We'll need to get our stock **Nougat** Samsung firmware, that we'll use as a base to work on. Head over to https://samfw.com/ , and type in your model no. to find the firmware you need. <br>
2. Target these **CSCs** when given the choice, as they offer the most features/compatibility:<br>
- BTU <br>
- XSA <br>
- XSG <br>
- XFA <br>
- KOO <br>
Download only **one** of the CSCs, and follow this priority of availability in CSCs, in this order. For example, if BTU is not available, then get XSA. If XSA is not available, then get XSG and so forth. Hit the "**"Download in browser"**, and wait for it to download. <br>
3. Also ensure that you have extracted the "**Vanity OS - Dev Kit**" zip file that you downloaded, since you'll need a lot of the files within this.

**Step 2: Extracting and decrypting the firmware:** <br>
1. Now that we have our firmwares, store them in a new folder. Label the folder as "Classy <insert model of device>", and place the **Classy Kitchen Executable**, in this folder.
2. Double click the Classy Kitchen executable, and wait for it to load. Once it loads, click "**Create New Project**. <br>
3. Once you do this, it should open a new prompt, asking where you want to pull the firmware source from. Click on "**From PC (Browse for one)**", and then select the firmware zip file that you downloaded. <br>
4. It will now ask for a project name. Name it **"Performante 1.0 - <insert model number> - <insert today's date>"**. After this, it will start extracting. <br>
5. It will finally ask to input a name for the **flashing of the ROM**. Just input whatever random name you want, as we will have to rebuild the installer script later.
   
**Step 3: Running the first De-skin scripts:** <br>
1. Once the firmware extracts, click on the **ROM Utils** button, and click on **Debloat/Bloat ROM**. <br>
2. Once you click on this, the windows explorer menu will open. Select the **Nougat Performante MDB** file, which is stored with the "**Vanity OS - Dev Kit**" folder that you extracted earlier. The kitchen will now begin removing and de-skinning the firmware. Once this is done, we can begin dekinning the firmware further by editing both the feature files, as well as the camera_feature files.
   
**Step 4: De-skinning Floating_feature:** <br>
1. For this section, you will need to dive into the system files, to begin removing features, and any other un-necessary files. First go into the **Classy Kitchen** folder, and into the folder called **Project**. Once there, go into the folder called **system**, and then the **etc** folder.<br>
2. Within here, you will now see a file called **floating_feature**. Open this file on you're preferred IDE or just open it in plain old Notepad. <br>
**Before you continue, please ensure that you make a backup of this file, as if you make a change that you didn't intend, or ever need to reference it again, you'll have to rextract the entire firmware to get this singular file, so a backup of this file is HIGHLY recommended**.<br>
3. Now keep the original factory **floating_feature** file in splitscreen on the left, and naviagate to the **Vanity OS - Dev Kit** folder, and open the file called "**NP - floating_feature.xml**. Put this file in splitscreen and compare the two.<br>
4. Looking at the two files, you will notice that factory floating_feature file, has significantly more lines in comparison to the NP file. What you want to do, it to start **removing** lines that are in the factory file, but are not in the NP file. **Please ensure you are careful when deleting these lines, since making a mistake such as leaving a bracket unclosed, or removing the wrong file, will result in the ROM bootlooping or unintended feature breaks. I have extensively tested the removal of the lines that I have selected, so I can verify that these do not cause issues. If you want to remove more lines, then feel free to experiment, but DO NOT RELEASE THE BUILD WITHOUT TESTING.** <br>
5. Once you have removed all the lines, head to the particular line: **<SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>Galaxy Tab S2</SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>**. Now your line may look a little different, depending on the model that you are building for, but that doesn't matter. Over here, edit the name to say "Performante <insert device name here>". A finished version, looks like this: **<SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>Performante - Tab S2</SEC_FLOATING_FEATURE_SETTINGS_CONFIG_BRAND_NAME>**.
6. After you have done this, save the new factory file, and you can move on to the next step.

**Step 5: Cameradata:** <br>
**Note: Since this section does not have a direct file to compare too, if you are uncomfortable doing this without a reference point, you may skip this section.** <br>
1. Now that we finished the floating_feature file de-skin, we can now move on to the next component, which is the **cameradata**. Go back one directory from inside the **etc** folder, and you will see the entire system again. You'll see a folder called **cameradata**. Go inside it, and open the **camera_feature** file within it. Again you may use any IDE or something as simple as Notepad will still work.<br>
2. Once within it, look at the code within. Under the **Modes** section, delete any modes that are un-necessary such as **Panorama, Continuous_Shot, Food, & 360**. **Note: Please be just as careful here, as removing the wrong mode, or leaving an unfinished bracket will cause the camera app to always crashing on launch.** <br>
3. Once this is done, save the file, and we are almost done! <br>

**Step 6: Build.prop editing:** <br>


