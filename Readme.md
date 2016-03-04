=====================================================================
High-Precision Software Directory
=====================================================================
* This code is from
* http://crd-legacy.lbl.gov/~dhbailey/mpdist/ 
* This is a test for building and running on windows with VS2015

=====================================================================
To re-build their arprec-2.2.18.tar.gz, on a windows platform. Mine was 8.1
=====================================================================
* (1) Untar to directory
* (2) Create new directory, such as arprec_t
* (3) copy over directories source and include
* (4) copy over file config.h 
* (5) copy over a test file.  I tested c_mp_test.c and renamed to c_mp_test.cc
* (6) Used VS2015, Update #2
* (7) With VS2015, it's a console application. Must select from toolbar Build/Configuration Manager  
*    Make this x64.  (x86 is still buggy anyway ) 
* (8) edit write.cpp, as in below:

                        
* bool mp_real::write(ostream &s, int precision, int width, int expn_width, 
*   ...
*  // return( s << str != 0 );
*   return true; // nick
* }	
