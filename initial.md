

**Project description:** Simplicity Studio Installers Improvements

<ul>
  <li>customers who cannot use the online installer for internet connection reasons</li>
  <li>customer who need a simpler installation experience and dont need/want to update the software and tools often</li>
  <li>training lab adminstrators who need installers availabe that include all the needed tools and SDK's</li>
</ul>


## Architecture

Each time a new version of Simplicity Studio is published, the Jenkins job responsible for the creation of the offline installers are trigged ( as a downstream job of the Publish public jenkins job).

Installation is done headless on a jenkins server using the scripting interface, and the resulting artifacts package appropriately (.iso, .dmg, .tar). Different variations of the offline installers are available ( eg: 8 bit / 32 bit / Sensors etc ). The offline installers will only have the latest SDK's installed. Each time the job is run the artifacts are pushed to aws, provided tehy are not an invalid installation.

Jenkins => Shell scripting => Python Script => Studio module

Jenkins job passes the target family, ( 8 bit / 32 bit / or a combination 8 bit - 32 bit ) the mirror location ( from where to fetch the base image and ) and the update sites.

The base image of Studio is fetched from the mirror location and extracted in a jenkins server. The python script is executed which communicates to the Studio module via the scripting interface and the relevanat packages for the target family is installed. On succesfull installation and if the version is valid the artifacts are created and pushed to aws.

### 1. Client

Silicon Labs Austin Texas
 
### 2.  Duration

 Aug 2016 - July 2018

### 3. Technologies used. 
Jenkins, shell scripting, Python, Java, SWT, OSGi Services, JFace, RCP, Git ,Windows 10

### 4. Role 

Individual Contributor

### 5. Responsilbilities

Implementing offline installers
