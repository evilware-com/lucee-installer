# Lucee Installer #

BitRock Installer XML config and files for creating the Lucee installers for Windows and Linux.

Bitrock has provided LAS with an Enterprise license for InstallBuilder, it's not in source source control

Forked from the great work by Vivotech, <https://github.com/viviotech/lucee-installer>, LAS is now managing the Lucee Installer Releases.

Note: You must build the Linux Installer on Linux, otherwise the file permissions like execute are missing.

## Build Preparation ##

None of the main binaries are checked into source control, the following manual steps are required:

The Lucee loader jar goes into the `lucee/lucee/lib` folder, i.e. <https://cdn.lucee.org/lucee-5.3.9.166.jar>

Download and extract the Tomcat 9 distribution into the `lucee/tomcat9/tomcat` folder, make sure you use the `tar.gz` version for Linux or the `.zip` version for Windows

Delete the `lucee/tomcat9/tomcat/webapps/` folder (Lucee has it's own)

Copy the customised `lucee/tomcat9/tomcat-lucee-conf` Lucee Tomcat configuration files over the extracted Tomcat distribution files  in `lucee/tomcat9/tomcat`.

Download the Windows or Linux 64-bit JREs from <https://adoptopenjdk.net/releases.html> and extract them into the appropriate `/jre` folders (delete the manual directory from the linux JRE)

Download and install the InstallBuilder Enterprise Edition <https://installbuilder.com/> make sure it's x64 version

Update the Version Number under Product Details in InstallBuilder

your file directory structure should look as follows

    /lucee-installer/
    ---/jre/
    ---/linux/
    ---/lucee/
    ---/mod_cfml/
    ---/tomcat9/
    ------------/bin/
    ------------/conf/
    ------------/lib/
    ------------/logs/
    ------------/webapps/
    ------------/work/
    ------------BUILDING.txt
    ------------CONTRIBUTING.md
    ------------LICENSE
    ------------NOTICE
    ------------README.md
    ------------RELEASE-NOTES
    ------------RUNNING.txt
    ---/translations/
    ---/windows/
        .gitignore
        license.txt
        lucee.ico
        lucee.xml
        lucee-logo.png
        lucee-side.png
        README.md
        sha512sums.txt
        splash.png
        tomcat.ico

## Building the Installer ##

Simply open the [lucee/lucee.xml](lucee/lucee.xml) file in InstallBuilder and click the Build icon.

## Support ##

Please first post any support questions to the Lucee Dev Forum <https://dev.lucee.org/>

Issues are in Lucee's Issue Tracker <https://luceeserver.atlassian.net/issues/?jql=labels%20%3D%20%22installer%22>
