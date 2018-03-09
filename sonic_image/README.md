---  How to come out the sonic image  ---

  In linux command modee, using the following commands to come out the image

   cat sonic-broadcom.tar.bz2.part* > sonic-broadcom.tar.bz2.

   tar -jxvf sonic-broadcom.tar.bz2.

  Then you could install "sonic-broadcom.bin" like ONIE's NOS way to install.

---  How to use the broadcom's configuration file  ---

  In this image of ag5648's the broadcom configuration,th-ag5648-48x25G+6x100G.config.bcm, is not 
  
  include in the SAI image, so you need to put it manually. Please do the folowing steps to make sure 

  broadcom's configuration is loaded.

    1. Copy the "th-ag5648-48x25G+6x100G.config.bcm" to /tmp on ag5648

    2. Type "docker ps " and make sure you can see the syncd container is running
 
    3. Copy the "th-ag5648-48x25G+6x100G.config.bcm" to syncd container via typing

          "docker cp /tmp/th-ag5648-48x25G+6x100G.config.bcm syncd:/etc/bcm"

    4. reboot the devices

    5. Type "bcmcmd ps" in command lind and you should see all the ports status


  You only  did those steps once.



