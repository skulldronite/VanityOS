# VanityOS
All required information, files and scripts on the project known as Vanity OS. Created by Vishan Karunaratne, and released on XDA by the alias Skulldron. Props to [Sourajit Karmakar](https://github.com/sourajitk) for helping with formatting, as well as the developer of our fabled kitchen, Classy Kitchen.

**What is Vanity OS?**

Vanity OS is a custom firmware, that prioritizes performance and battery life, for all the devices that it is built for. It is built primarily for Samsung devices, and utilizes the stock firmware that is provided by Samsung, to maintain the best available drivers, as well as to ensure that any under the hood optimizations done by Samsung themselves, carry over. It accomplishes this through a very heavy, and thorough de-skinning process, which involves removing and vacating as many unnecessary apps, media, features and framework.

**Android version compatibility:**

Vanity OS is primarily supported over three android versions, which are **Nougat**, **Oreo** & **Pie**. While some of the scripts available here may be compatible with future versions of Android (in particular, Android Q & R), currently the kitchen that is utilized does not support treble based systems, and hence why there is no testing available for these android versions. If a workaround is found, either through a new kitchen, or a way to allow the old kitchen to create functioning META-INF's for the newer android versions, it will be limited to these three.

**Flavours:**

There are three "flavours" available for Vanity OS. A flavour is best described as a specilization of the particular Android version, with each one having a unique style and/or goal in terms of both appearance or depth of de-skinning. I will now highlight the three flavours seperately below. Pick the one you want to build, based on the Android version you currently have.

**Performante - Nougat 7.0 & 7.1.1:**

The Performante series, is what would be considering the deepest de-skinning out of the three flavours. It features the removal of almost all native Samsung apps, with low memory/ high performance application replacements instead being made available instead. An example of this, is replacing the stock Samsung Music app, which is heavy on a user interface level, with something light, such as Eleven Music by Lineage OS, which consumes a significantly smaller memory footprint, with simpler user interface elements, allowing for better rendering on the host device, which is especially noticeable, if the host device's hardware is weak. This flavour also heavily de-skins floating-feature files, usually halfing them in size, as well as the largest stripping of camera modes from the camera-featurev7 files.

**Vanity OS Legacy - 8.0.0 & 8.1.0:**

The Legacy series, is the operating system of choice, for those who still want OEM applications, such as Samsung Dialer, along with still containing a relatively deep de-skin. Out of the three flavours, this one has the lightest deskin, since Samsung Oreo firmwares were a bit strange when it came to modularity, and since this means we can't remove everything, it was better to embrace the change, and keep this version as balanced as we could, in terms of feature set + performance. The scripts are still relatively aggressive, but are nowhere near as aggressive as Performante.

**Vanity OS - 9.0:**

Finally, we reach Vanity OS itself, and this is where the philosophy began. Vanity OS is the ultimate combination of performance, and OEM features, with de-skin scripts that run quite deep, as well as almost full modularity, allowing for major revisions to features and framework. While again, this doesn't go as deep as Performante, it is still a very significant update, and some of the ROMs created with its tools are some of the best around in terms of performance, battery & features.

**How can I build a variant?**

Within this directory, I have created a guide on what files you need, how to utilize the scripts, what to remove manually by hand, and what you'll need to add back in certain flavours (**Give particular attention to Performante**). This guide should be easy to follow, but in-case something goes wrong, or you have a question for me, you can find me on the official Vanity OS telegram group, or message me on XDA.

**Telegram Group Link:** [VanityOS Group](https://t.me/VanityOS)

**XDA Account Username:** [XDA Forums](https://xdaforums.com/m/skulldron.7243932/)

**Conclusion:**

Well, I hope that whoever you are, whether you're someone who wants to learn Android development, and want to start with something small in-terms of development, I hope you find success in making one of these flavours. I also want to make sure you understand, that any work you create using my scripts is **your** work, and you will never need to credit me. However, I would love to see your work, so please do tag me, if you do make something! If you are simply a user, who clicked on this link to view the source code of this firmware, I hope that you are enjoying your experience with Vanity OS, regardless of the flavour, and I wish you a bugless experience. That's it for now, so please check the other documents for further information, on whatever you need.
