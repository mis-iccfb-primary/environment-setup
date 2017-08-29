# Supported Development Environment

* Ubuntu 15 or 16
* Eclipse
* Java Development Kit 1.8

## Ubuntu 15 or 16
Although Ubuntu can be ran as a VM through VirtualBox, students had multiple issues with this setup - low end computers or Windows Home Edition not supporting virtualization.  I recommend setting up a Ubuntu VM on Amazon Web Services to run your development environment.  The rest of this document assumes Ubuntu running in AWS.


### Launching EC2 Instance for Development.

Log into the AWS Developer's Console -

https://aws.amazon.com/console/

* Click "Launch Instance"
* Choose the Ubuntu machine image
* Choose the t2.medium instance type
* Click "Review and Launch"

You will need to setup the Security Groups from the Review Instance Launch page.  

* Click "Edit security group"
* Click "Add Rule" and add rules for these TCP ports
  * 8080 - Used in development
  * 3389 - Remote Desktop

**Recommended** - For a more secure setup, select "My IP" from the drop down for the Source field when adding a rule.  Your IP will auto populate into the "CIDR, IP or Security Group" field.  Your IP will most likely change frequently.  You will need to update the source IP from the AWS Console before accessing the VMs.

Click "Launch" and you will be presented with a dialogue to select or create a key pair.  This key pair is very important and must kept in a secure location.

### SSH'ing into your Instance

SSH'ing into your instance from OSX or Linux -

http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html

SSH'ing into your instance from Windows using Putty -

http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html

## Setting up a Desktop

The following article goes through the steps on how to setup a desktop for your Ubuntu EC2 instance.  There are a few things occurring as you go through the steps.  Here is a break down to help you understand these instructions -

* Steps 1-3 are connecting and preparing the VM
* Steps 4-8 are setting up password access
* Steps 9-10 are installing the desktop
* Steps 11-16 are setting up remote desktop access
* Rest of the steps are connecting to the VM

A couple of notes -
* The article states Ubuntu 14.04.  These will work for newer Ubuntu versions.
* The article states accessing from Windows.  Any Remote Desktop Application will work.
* Ensure your password created in step #7 is strong.  A strong password will help keep the instance secure.

https://aws.amazon.com/premiumsupport/knowledge-center/connect-to-linux-desktop-from-windows/

Use a remote desktop client to access the VM.

## Java Development Kit 8
You will need to install JDK 8 on the VM.  Use the following command -

    sudo apt install openjdk-8-jdk-headless

Verify the install -

    javac -version

## Eclipse
From your VM's desktop (Firefox is pre-installed), download the Eclipse Neon installer from -

https://www.eclipse.org

Launch the Eclipse installer and install Eclipse IDE for Java EE Developers.

## Application Code

### Git

Git should already be installed on your VM.  You can check by the following command -

    git --version

If Git isn't installed, you can install it via apt-get -

    apt-get install git

If you are not familiar with Git or source control, the online documentation is great -

https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control

### Github

If you do not have a Github account, create one -

https://github.com/

This simple "Hello World" example gives an overview of Github -

https://guides.github.com/activities/hello-world/

### Forking the Quote Application

You will need to fork the Quote application that we will be using for this class -

https://github.com/mis-iccfb-primary/quote-app-monolith

Once forked, clone the application from your repository.

The Quote application's repository contains a Readme that describes how to build and run the application.
