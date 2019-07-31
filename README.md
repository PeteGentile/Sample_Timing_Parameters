# Sample_Timing_Parameters
Notebook for the Bayesian implementation of Pulsar Timing

Included in this repo is the profile domain code I've written in Jupyter notebook form. It's useful to play around/test with, but I wouldn't actually run the code from here because you'd have to keep the notebook running the entire time the code runs, which is a long time.

Note that all documentation was written in a conversational style aimed at new grad students and therefore assumes some familiarity with pulsars and python, but not a deep knowledge of either.

Anyway, to run this, you'll need 3 things:

1. An initial par file.
2. A "metafile". This is just a text file with each line being the name of a data file you'd like to include in the timing solution. If you want an example, there's one on Bowser here: `/hyrule/data/users/pgentile/prof_domain/Profile_Domain_Timing/datafiles.txt`
3. A "model file". This is a file that contains a list of the parameters of the gaussians that have been fit to the profile. You'll have to make this yourself. To do that, take the metafile from step 2 and run the following command:

`python2 /home/pgentile/.local/lib/python2.7/site-packages/ppgauss.py -M metafile_you_made.txt`
    
That'll bring up a display with a pulse profile, and will print out some instructions on how to fit gaussians to the profile. Follow them and get a "good enough" fit. Then press "p" to print out that fit. The text that gets spat out can be put into a text file.
    
Note that this code (the ppgauss one) was written by Tim Pennucci in python2. One TODO is to convert ppgauss to python3, but until then, it needs to be run in python2.
    
Another thing to note is that this code assumes the data have been folded with something like `fold_psrfits`.

Once you have those files, you should be set to start running the code. 

A useful resource is Lindley's paper on Bayesian pulsar analysis, found here:

https://arxiv.org/pdf/1412.1427.pdf
