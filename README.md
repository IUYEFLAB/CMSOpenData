# CMSOpenData

#### Installing Docker ####

After selecting the docker installation package suitable for the operating system from the Docker official site, the docker application is run with a simple application installation logic. Packages are obviously available for Windows and Linux, but MacOs users should not forget the difference between arm and amd packages, and for Mac computers with M1 chip, the arm-based Docker package should be downloaded. At this point, the wrongly downloaded package causes the process to go wrong.

You can see the link : https://docs.docker.com/desktop/mac/apple-silicon/

After you finish the download, you can check your system by taking a test drive from the example in the CMSSW paper where you can find here : https://cms-opendata-workshop.github.io/workshop2022-lesson-docker/02-installing-docker/index.html

The Cms open data container that should be used for CMSSW is quite large (about 6.6 Gb) so it may take time to download. Likewise, the root and python libraries required for operation have a size of about 1 Gb. Downloading all 3 containers required for cmssw in Docker takes about 20 Gb of memory in total. Don't let this worry you.

After completing the installation and container downloads, it is quite possible to encounter error 137 when trying the examples given in the paper (at least for MacOs M1 users). This error is caused by Docker not having enough memory available for as long as we want it to run. The solution is to increase the size of memory Docker can use. For this, increasing the memory and swap values to the end in Docker--> Resources path will solve the error. (8Gb and 4Gb)

You can use this link to download containers and take test drives : https://cms-opendata-workshop.github.io/workshop2022-lesson-docker/03-docker-for-cms-opendata/index.html

Using Root for CMSSW takes place via a browser. If you want to see the histograms of an output you have obtained, all you have to do is use an interface called VNC.

Start_vnc is the commands used to start the interface and stop_vnc are the commands used to terminate the interface. One of the most important points to note here is that root will not run before the start_vnc command. If you have a problem with root, make sure you run this command first.The other most important point is that the VNC interface started for a process is stopped in the same way when that process ends. If you switch to other containers without using the stop_vnc command, you may get errors both in the interface and in the terminal.

If you wanted to delete one of the Docker containers, the command to use was docker rm "container name". But if you delete a container, it will only delete within Docker, not from the local machine. So inside your local computer you should delete Users --> libraries --> com.docker.docker. (If you want to reinstall the whole setup or if you want to delete it permanently) After deleting, your computer's memory may still appear full, try restarting your machine for this.

Short Notes :

CmsSw contains 2015 Run 2 data at AOD and miniAOD level.

The scram b command is used to compile the edited code.

The cmsRun command is used to run the code.
