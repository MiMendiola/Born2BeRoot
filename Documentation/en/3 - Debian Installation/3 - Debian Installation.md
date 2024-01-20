# 3 - Debian Installation

Before we begin, let's enlarge the window for better visibility. Click on the PC icon, hover over `Virtual Screen 1`, and scale it to 200%.

![ ](./Screen_Shot_2023-10-04_at_6.58.35_PM.png)

 

## Let's start the installation.

To navigate through the installation, use the `Arrows` to move and `Enter` to confirm actions.

1. Start by moving to `Install` and initiate the installation by pressing `Enter`.

    ![ ](./Screen_Shot_2023-10-04_at_7.08.22_PM.png)
    
     
    
2. Use the default language or choose your preferred one; in our case, we'll use English.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.11.49_PM.png)
    
     
    
3. Enter your country or residence zone; in my case, I'll select `other`.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.14.07_PM.png)
    
     
    
4. Next, select your continent, `Europe` in my case.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.14.32_PM.png)
    
     
    
5. Lastly, choose your country, `Spain` 🇪🇸, in my case.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.14.52_PM.png)
    
     
    
6. Now, set your local settings to `United States`. This will take a few seconds.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.19.36_PM.png)
    
     
    
7. Select `American English` as the keyboard configuration to avoid future key issues.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.19.51_PM.png)
    
     
    
8. Choose the hostname for your machine. It should be your `login + 42` in the end.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.23.02_PM.png)
    
     
    
9. Skip the next step; we won't mention anything about a Domain name.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.23.36_PM.png)
    
     
    
10. Set the password for the system administrator. If you want to view the password, `Tab` to the `Show Password in Clear` option and press `Space`. Follow these steps for a valid password:
    1. Must be at least 10 characters.
    2. Must contain at least one uppercase letter.
    3. Must contain at least one lowercase letter.
    4. Must contain at least one number.
    5. Must not have more than 3 identical consecutive characters.
    6. Must not include the username.
    7. Must have at least 7 characters that were not in the previous password (this doesn't apply to root).
    
    Important: Note or take a photo of this password to avoid losing it. The displayed password is valid, but I recommend using a new one.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.32.40_PM.png)
    
     
    
11. Rewrite the password to confirm.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.38.20_PM.png)
    
     
    
12. Add a new user, in addition to the system's root; you can name it as you like.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.44.42_PM.png)
    
     
    
13. Enter the username again.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.44.59_PM.png)
    
     
    
14. Now, follow the same procedure to set the password for your user.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.48.29_PM.png)
    
     
    
15. Confirm the password for your user.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.49.02_PM.png)
    
     
    
16. Select your location and wait for a few seconds.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.52.54_PM.png)
    
     
    
17. If you want to proceed without the bonus, you can see how to do it in [*Without Bonuses](https://github.com/gemartin99/Born2beroot-Tutorial#3--instalaci%C3%B3n-debian-).* If you're doing it with bonuses, select `Manual`. This allows us to edit the partitions all at once.
    
    ![ ](./Screen_Shot_2023-10-04_at_7.53.53_PM.png)
    
     
    
18. At this point, we don't have any partitions yet. To create them, choose the device you want to work on; in our case, it's the only one available.
    
    ![ ](./Screen_Shot_2023-10-05_at_4.59.12_PM.png)
    
     
    
19. This message tells us that if there are existing partitions on the device, they will be deleted. Confirm that you want to create a new empty partition table. `Accept` the message.
    
    ![ ](./Screen_Shot_2023-10-05_at_4.59.36_PM.png)
    
     
    
20. Now select the new partition table you just created.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.04.51_PM.png)
    
     
    
21. Create a new partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.05.14_PM.png)
    
     
    
22. As per the PDF instructions, create a partition of `500m`
    
    ![ ](./Screen_Shot_2023-10-05_at_5.05.46_PM.png)
    
     
    
23. As this first partition will be where the operating system is installed, we will choose `Primary`.
    
    Brief description of all [partition types](Tipos%20de%20Particiones.md).
    
    ![ ](./Screen_Shot_2023-10-05_at_5.07.53_PM.png)
    
     
    
24. Since we want it to be copied to the beginning, we select `Comienzo`.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.09.08_PM.png)
    
     
    
25. We will change the mount point of our partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.12.50_PM.png)
    
     
    
26. Select "boot" as the mount point for our partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.15.40_PM.png)
    
     
    
27. And we finish configuring the partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.15.50_PM.png)
    
     
    
28. Our created partition should now appear, and next, we will create a logical partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.24.09_PM.png)
    
     
    
29. Create a new partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.24.38_PM.png)
    
     
    
30. Use the maximum available space for this partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.24.54_PM.png)
    
     
    
31. Set it as a `Logical` partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.30.00_PM.png)
    
     
    
32. Modify the mount point.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.33.06_PM.png)
    
     
    
33. Choose the option not to mount it.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.33.51_PM.png)
    
     
    
34. And finish configuring this partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.34.03_PM.png)
    
     
    
35. Now we start configuring the `Encrypted Volumes`to encrypt our partitions.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.35.11_PM.png)
    
     
    
36. Accept the confirmation message and wait a few seconds.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.35.18_PM.png)
    
     
    
37. Create the encrypted volumes.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.36.47_PM.png)
    
     
    
38. Select the partition for encryption.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.37.20_PM.png)
    
     
    
39. And finish configuring the encrypted partition.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.38.23_PM.png)
    
     
    
40. With that encrypted volume, finish by clicking on `Finish`.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.39.10_PM.png)
    
     
    
41. Accept the confirmation message stating that it will encrypt everything inside and won't take long to finish.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.40.33_PM.png)
    
     
    
42. Since the partition is empty, there's nothing to encrypt, so click on `Cancelar`.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.41.30_PM.png)
    
     
    
43. Now we will set a password, which will be the encryption passphrase.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.44.24_PM.png)
    
     
    
44. Repeat the password and wait a few seconds.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.44.54_PM.png)
    
     
    
45. Now we continue configuring the `Logical Volume Manager`.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.45.39_PM.png)
    
     
    
46. Accept the confirmation message since we agree to change the disk.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.47.47_PM.png)
    
     
    
47. Create a new `volume group (groups partitions)`.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.50.00_PM.png)
    
     
    
48. Add the group with the name `LVMGroup` as specified in the PDF.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.50.45_PM.png)
    
     
    
49. And select the partition to create the group.
    
    ![ ](./Screen_Shot_2023-10-05_at_5.50.57_PM.png)
    
     
    
50. Now we need to create all the necessary logical partitions. Below, you can see the sequence of actions to be taken, along with the size in gigabytes for each partition.
    1. `root` - `10g`
    2. `swap` - `2.3g`
    3. `home` - `5g`
    4. `var` - `3g`
    5. `srv` - `3g`
    6. `tmp` - `3g`
    7. `var-log` - `4g`
    
    ![ You have to follow these steps until you have completed all the partitions.](./Screen_Shot_2023-10-05_at_5.54.31_PM.png)
    
     You have to follow these steps until you have completed all the partitions.
    
    ![Select the group where you will create it, the only available one.](./Screen_Shot_2023-10-05_at_5.57.56_PM.png)
    
    Select the group where you will create it, the only available one.
    
    ![Enter the name of the logical unit. From root to var-log.](./Screen_Shot_2023-10-05_at_5.58.07_PM.png)
    
    Enter the name of the logical unit. From root to var-log.
    
    ![Next is the size we will use for that unit.](./Screen_Shot_2023-10-05_at_5.58.22_PM.png)
    
    Next is the size we will use for that unit.
    
51. Once all are finished, we will complete the configuration of the logical volume manager.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.07.08_PM.png)
    
     
    
52. Now, all the logical partitions we just created will appear. We need to configure them by selecting the file system we want and the respective mount point for each one. All will be the same except for `swap` and `var-log`
    
    ![These will be all partitions except for swap and var-log.](./Screen_Shot_2023-10-05_at_6.15.05_PM.png)
    
    These will be all partitions except for swap and var-log.
    
    ![We must choose a file system as it does not have one at this moment.](./Screen_Shot_2023-10-05_at_6.17.55_PM.png)
    
    We must choose a file system as it does not have one at this moment.
    
    ![In all common ones, we will select `Ext4 journaling file system` .](./Screen_Shot_2023-10-05_at_6.18.10_PM.png)
    
    In all common ones, we will select `Ext4 journaling file system` .
    
    ![Now we will change to their respective mount point.](./Screen_Shot_2023-10-05_at_6.18.19_PM.png)
    
    Now we will change to their respective mount point.
    
    ![For home, we will select /home.](./Screen_Shot_2023-10-05_at_6.18.25_PM.png)
    
    For home, we will select /home.
    
    ![And we will finish with the configuration.](./Screen_Shot_2023-10-05_at_6.18.34_PM.png)
    
    And we will finish with the configuration.
    
    ![For swap, we will select the swap area.](./Screen_Shot_2023-10-05_at_6.22.05_PM.png)
    
    For swap, we will select the swap area.
    
    ![And we will finish configuring this partition.](./Screen_Shot_2023-10-05_at_6.23.02_PM.png)
    
    And we will finish configuring this partition.
    
    ![For var-log, we will follow the next steps.](./Screen_Shot_2023-10-05_at_6.29.49_PM.png)
    
    For var-log, we will follow the next steps.
    
    ![We must choose a file system as it does not have one at this moment.](./Screen_Shot_2023-10-05_at_6.30.51_PM.png)
    
    We must choose a file system as it does not have one at this moment.
    
    ![In all common ones, we will select `Ext4 journaling file system` .](./Screen_Shot_2023-10-05_at_6.30.55_PM.png)
    
    In all common ones, we will select `Ext4 journaling file system` .
    
    ![Now we will change to their respective mount point.](./Screen_Shot_2023-10-05_at_6.31.03_PM.png)
    
    Now we will change to their respective mount point.
    
    ![We will manually enter the mount point.](./Screen_Shot_2023-10-05_at_6.31.09_PM.png)
    
    We will manually enter the mount point.
    
    ![We enter /var/log.](./Screen_Shot_2023-10-05_at_6.31.32_PM.png)
    
    We enter /var/log.
    
    ![And we finish with the last partition.](./Screen_Shot_2023-10-05_at_6.31.39_PM.png)
    
    And we finish with the last partition.
    
53. Once all the steps are completed, click on finish partitioning and write the changes.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.32.10_PM.png)
    
     
    
54. Now, accept the message, and the changes made will be saved. Make sure they match the screenshot. This process will take a few minutes.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.32.20_PM.png)
    
     
    
55. Select the option `No` as we do not need additional packages.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.45.30_PM.png)
    
     
    
56. Choose your country.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.47.02_PM.png)
    
     
    
57. Choose `deb.debian.org`, which is where we will have a better connection according to our region.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.47.51_PM.png)
    
     
    
58. Click on `Continue` and leave it empty.
    
    ![ ](./Screen_Shot_2023-10-05_at_6.49.09_PM.png)
    
     
    
59. Select `No` so that statistics are not viewed.
    
    ![ ](./Screen_Shot_2023-10-05_at_7.03.30_PM.png)
    
     
    
60. Remove all software options and click on `Continue`.
    
    ![ ](./Screen_Shot_2023-10-05_at_7.03.59_PM.png)
    
     
    
61. Choose `Yes` to install `GRUB-PC` on the disk.
    
    ![ ](./Screen_Shot_2023-10-05_at_7.04.56_PM.png)
    
     
    
62. Select the device to boot our installation `/dev/sda (ata_VBOX_HARDDISK)`.
    
    ![ ](./Screen_Shot_2023-10-05_at_7.05.03_PM.png)
    
     
    
63. Finally, click on `Continue` to finish our `Debian installation`.
    
    ![ ](./Screen_Shot_2023-10-05_at_7.06.22_PM.png)
    
     
    
64. After this, proceed to configure your virtual machine.