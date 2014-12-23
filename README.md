README--SegoviaSource

Sorry this directory is a bit of a mess; the Segovia sample application didn't
bother with resource directories, etc., and we didn't bother fixing that.

Basically, throw all the files needed at runtime in this directory, including
.jar dependencies and images, with the PalmSecureSample_Java.jar file that
contains the main application, and run StartSample.sh.

The .so files seem to be the binaries containing the actual library; I'm not
sure which are strictly necessary, and so haven't touched them since downloading
the sample.  The two .jar libraries are the Java interface to the binaries and
the basic csv library we used.  All of the images and sounds the application
uses are thrown into the top level directory.  When the application is running,
it will store palm vein data in .dat files and the recipient csv in the /Data
subdirectory.  The program also keeps log files, which are stored in /Log.
These subdirectories can be safely deleted if you want to start with a fresh
enrollment 'database'.

Assuming you have followed Fujitsu's installation instructions, the most common
error, by far, is an error dialog that says "PalmSecure Library Error" with
a bunch of hexadecimal codes.  The codes are outlined in the PalmSecure sample
docs, but we have never seen any error but the one that deals with an issue
connecting to the reader.  If you see this, verify that the palm reader is
connected to the VM in the 'Devices' menu in the VirtualBox menu bar.  If it is,
you may need to reinstall the palm vein reader driver by following the steps
in the driver documentation.  This error is thrown by the Java application and
defined in the Fujitsu library, so if you're seeing it, the application itself
must be running and talking to the Java library.
