# Instructions for Windows #

1.  Download [Strawberry Perl](https://strawberryperl.com/).  The portable .Zip with PDL is recommended.
2.  Extract Strawberry Perl .ZIP file.
3.  Run ```portableshell.bat``` which is in main directory.
4.  Install libraries by running these commands: ```cpanm Net::SSLeay``` ```cpanm IO::Socket``` ```cpanm LWP::Protocol```
5.  In file, ```/perl/lib/File/Copy.pm```, comment out ```BEGIN { eval q{ use Time::HiRes qw( stat utime ) } };``` by putting ```#``` at the start of the line.  [Source](https://bobhowto.wordpress.com/2019/11/01/how-to-fix-timehiresutime-unimplemented-in-this-platform-in-perl-on-windows/).
6.  Change the zap2xml.pl perl script from ```$urlRoot = 'https://tvlistings.zap2it.com/';``` to ```$urlRoot = 'https://tvlistings.gracenote.com/';```
7.  Save and run the perl script: ```perl zap2xml.pl```.  The command line parameters will be displayed.
8.  The user accounts for zap2it.com were moved to gracenote.com so it should work the same.
9.  If you need an account, register with https://tvlistings.gracenote.com/grid-affiliates.html?aid=lat
10.  Try logging in using ```perl zap2xml.pl -u (email) -p (password) -d 1```

# Creating .EXE file #
1. Run ```portableshell.bat``` which is in main directory.
2. Install library ```cpanm PAR::Packer```
3. Run ```pp -o zap2xml.exe zap2xml.pl -M Sub::Util```
4. Run ```zap2xml.exe```
