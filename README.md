# My background maintenance tasks for my Windows Work Computer
To regularly maintain my Windows Work Computer healthy I set tasks to check and repair my OS, clean trash and defrag or TRIM my disks. Why is this important? Stupid question. Don't you change the oil and fluids on your car, clean it, check your tires and send it to your mechanic for inspection regularly? __REMEMBER:__ _You are only as good as your tools. I am not joking._ 

You can do all of this via cmd.exe or powershell.exe, however GUI is going to be used here to illustrate and help people who are still unconfortable with terminals.

## Let's start
The very first thing you should do is Schedule a Task with Windows' Task Scheduler and create a folder called MyTasks or Personal (or whatever).
Then you'll create a task by right clicking that folder and choosing "Create Task...", and name it something coherent.

In "Configure for:" choose your Windows version, and click on "Run whether user is logged on or not" and if you're an Administrator and have privileges, also check the "Run at the highest privileges" option

Then jump to "Triggers" and click on "New", your timeframe is yours only, I don't know or care about your life, so schedule it accordingly to what fits you. I've choosen to run it monthly at the very last day.

Jumping to "Actions" you're going to add the following commands (one at a time) by clicking "New":
"dism /online /cleanup-image /checkhealth"
"dism /online /Cleanup-image /restorehealth"
"sfc /scannow"
"cleanmgr /sagerun:_n_" \[__NOTE:__ _n_ is a number between 1 and 255; choose one at will\]

Click "OK" and Type in your Password!

After that go to your cmd or powershell (if you're Admin, run as Admin) and execute the "cleanmgr /sageset:_n_" command. \[__NOTE:__ _n_ must be the same _n_ you've choosen before\]

It'll open a Disk Cleanup window, choose every option you want/need. I've choosen every option, because I want this ~~clean~~ sterilized.

Then we'll navigate to dfrgui.exe (a.k.a Defragment and Optimize Drives), and we'll turn on Sheduled Optimization by clicking "Change Settings" and setting our schedule and choosing ALL drives. I'm doing it Weekly. Also check "Increase task priority..." so it works as it should if it fails somehow.

Then go to your Settings App > System > Storage and turn on "Storage Sense".

Done, you've now configured the bare minimum of an "automated maintenace". I also use [Sycnex's Debloater](https://github.com/Sycnex/Windows10Debloater) so I uninstall every bullshit Microsoft decided it was funny to include with our installations, and other junk our computer brands included to the trashpile.
