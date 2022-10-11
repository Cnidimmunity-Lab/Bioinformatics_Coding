# Pegasus and Triton Setup 

This doc is here to assist in usage of the University of Miami (UM) superclusters (Pegasus and Triton). The SOP docs by UM’s Institute for Data Science and Computing (IDSC) can be confusing for new users. 

## Web links 

* IDSC Quick Links (and where to set up an account): [link](https://idsc.miami.edu/quick-links/)
* Pegasus User Guide: [link](https://acs-docs.readthedocs.io/pegasus/README.html)
* Triton User Guide: [link](https://acs-docs.readthedocs.io/triton/README.html)
* UM’s VPN Guide: [link](
https://security.it.miami.edu/stay-safe/sec-articles/unsupported-remote-access-tools/index.html)
* LSF system bsub command help: [reference link](https://www.ibm.com/docs/en/spectrum-lsf/10.1.0?topic=reference-bsub), [options link](https://www.ibm.com/docs/en/spectrum-lsf/10.1.0?topic=bsub-options)

## How to get set up

1. Set up an account using the IDSC Quick Links page
2. Connect with Dr. Traylor-Knowles and confirm your usage and which supercluster you will be using. We are charged for our usage, so she may have specific instructions regarding grants 
3. Student users are allocated 250 Gb of space to their home folder; the lab also has extra space that is referred to as scratch space. 
  * To gain access to the scratch space, which has 2 TB allocated, you will need to fill out a form that should be available when you create your account. 
  * You will need  Dr. Traylor-Knowles’s approval for this. 

## Pegasus vs Triton

* Pegasus is older than Triton, and has more diversity of modules (pre-installed software) available
* Pegasus is also more commonly used, meaning that the wait time for your job to run could be longer
* Triton uses a rare architecture, meaning much fewer modules are available, and installing your own software can be frustrating when there isn’t a binary file for your software program that is compatible

**Conclusion: Pegasus should be your default choice, unless you know for certain that Triton will be more appropriate and you can work with the software requirements** 

## VPN access

* If you plan on using the supercomputer (logging in, submitting jobs, etc) off campus, then you will need to set up a UM-approved VPN to access the server. 
* The current software used for this is GlobalProtect, and the web link provided above in the Web link section provides instructions to install and a link to the Box folder with it

## How to log in

1. To connect to the supercomputer, open up your command line (Terminal for Mac, Command Prompt for Windows)
2. For Macs, use the ssh command to create a secure connection
  * Example: `ssh username@pegasus.ccs.miami.edu`
3. Login will prompt you for your password
4. The welcome page will list how much space your home directory has available, along with any scratch space accounts you have access to

*Note that the file path for the home directory is different across Pegasus and Triton (Pegasus should be /nethome/username; Triton is /home/username)

## Additional Information

* The superclusters are made up of nodes, which are made up of connected processors; when you log on to the remote server, you will be using the Login nodule; **do not run any large commands here.** Get off the login node. If you don’t, you will be at risk for irritating the IDSC and subject yourself to an angry email. 
* Lab scratch space paths:
  * The file path for Pegasus is `/scratch/projects/transcriptomics`
  * The file path for Triton is  `/scratch/coral_cellpops`
* If you have access to these spaces, you can move over to a node and charged to the space with:
  * `bsub -Is -P transcriptomics bash`
  * `bsub -Is -P coral_cellpops bash`
* To view the software available: `module avail`
* To view the software already queued: `module list`
* To load a particular software: e.g. `module load python/3.8.7`
* File transfers: FileZilla
  * This GUI is commonly used to transfer files between your local drive and the superclusters. While the ACS docs recommend it, UM has flagged it for malware and recommends against using it
  * If you know you need to use it, proceed with caution, and I recommend reaching out to UMIT to get it installed safely (https://security.it.miami.edu/stay-safe/sec-articles/filezilla-issues/index.html)
  * This malware issue was flagged several years ago (~2018 I think), so someone should follow up with UMIT to confirm this is still a concern
