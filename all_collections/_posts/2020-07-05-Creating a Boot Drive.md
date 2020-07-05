
<a id="org77d8534"></a>

# Bootable Drive Creation on Linux


<a id="orgda56df0"></a>

## This week I had the need to create a bootable drive with the aim to breathe some life into an old laptop. Below are the commends and comments to do this using the terminal in Ubuntu.


<a id="orgccf5316"></a>

## Check for all you mounted drivers using

    df

![img](/img/dfoutput.png)


<a id="org51bc40b"></a>

## This will print out all your drives into the terminal - you are looking for the USB drive you want to use as your bootable drive. Typically something like */dev/sdax/* where x is a number. In the above example my drive is */sdc1/*.

    sudo umount /path/where/mounted


<a id="orge1d4b0e"></a>

## This unmounts the drive - ready for your .iso to be written too.

    sudo dd bs=4M if=/point/to/.iso  of=/dev/yourdrive status=progress oflag=sync


<a id="org44ba568"></a>

## This will run through the process and - in a few minutes, you will have a bootable drive. If it doesn't boot run the dd command on the drive minus the number ie */SDA/* not */SDAx/*.

