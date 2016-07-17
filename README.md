VW DLibrary
========================================================================================================================

Common library for VW plug-ins.

## USING THE LIBRARY ###################################################################################################

See the [Wiki](https://bitbucket.org/dieterdworks/vw-dlibrary/wiki/Home) on how to use this library, especially the
[Examples section](https://bitbucket.org/dieterdworks/vw-dlibrary/wiki/browse/examples). Keep in mind that the wiki is
still work in progress. You can contribute all things you can't find and want in it.

### INSTALLATION #######################################################################################################

You'll find an `install.py` file with this library, to enable your uses to install your plugin more easily and also 
install the min. version of dlibrary need for your plugin to work. You just add this file to the .zip folder of your 
distribution for Vectorworks to pick it up.

Due to a bug in Vectorworks, the PreInstall script in install.vwx, which is also included, has to be ran in order to 
prepare Vectorworks for the installation, as the script uses drop-in functions, which aren't available at start-up.

### EXAMPLE ############################################################################################################

You'll find a working example in the dlibrary_test folder. It's a VW menu command which will open up a dialog with all 
possible controls as a reference. This is not complete, we'll add more examples and docs later...

## CONTRIBUTING ########################################################################################################

Everyone can contribute, and please do, so we can make this the best resource for Vectorworks plug-in developers to 
write great plug-ins fast and with ease!

### BRANCHES ###########################################################################################################

#### The MASTER branch #################################################################################################

The MASTER branch is our main branch with all versions tagged on it. So it will hold all versions of dlibrary. This will
reflect the releases of Vectorworks. For example, VW is now at version 2015, so we are also at version 2015. So through
the VW2015 version, we add to dlibrary for that version and make sure it stays backwards compatible. Off course there
can be code written for a future release and other code can be made obsolete, while still working! Once the next version
of Vectorworks is released, we do a cleanup of obsolete code and run all tests against the new vs api. We update our own
version to the new VW version and do an initial release. This process will continue throughout the whole MASTER branch.
This way, the user will only have one version of dlibrary for his VW installation with the same version number.
 
#### The HISTORY branches ##############################################################################################

Once we switch to the new VW version, we aren't able to do any more bugfixing for previous version, or add any new code
for people that really need it. VW itself doesn't do any more bugfixing of previous versions, but to give developers
time to update their code, and to still being able to satisfy users of older version, we'll need a way to apply bugfixes
and new features if needed. Therefore, before a new version is released, a HISTORY branch will be made for the old
version to make sure we can do bugfixes. The name of the branch should be `history/2015`.

#### The FEATURE branches ##############################################################################################

Writing a feature can take time and maybe isn't in time for the current release, also to make sure that there is enough
time to test etc, we'll need a way to work on a feature without breaking the MASTER branch. Therefore, for each feature
after the initial release, we'll work with FEATURE branches, named like `feature/feature-name`.

### CONTRIBUTION REMARKS ###############################################################################################

- Never use `_` for a throwaway variable, as VW seems to give special meaning to it!
- vs.py has been extended to add the things NNA didn't include like the Handle class. Make sure you leave this and check
when update the file with a new version!
- For the class docstring, always start with it's type, as the auto-generated documentation will use this to group and
render them in a specific way. Use one of these: Enum, Singleton.
- Always put the return type of properties in the docstring, as inspect can't get type hints from properties!
