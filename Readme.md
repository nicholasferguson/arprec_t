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

=====================================================================
c_mp_test.cc prints out
=====================================================================

*  pi = 10 ^ 0 x 3.1415926535897932384626433832795028841971693993751058209749445923
07816406286208998628034825342117067982148086513282306647093844609550582231725359
40812848111745028410270193852110555964462294895493038196442881097566593344612847
564823378678316527120190914564856692346034861045432664821339360726
*  sin(0.7) = 10 ^ -1 x 6.442176872376910536726143513987201830658138445736896447439
63088093829975449675664714626692168757705358303229380267588379310129212990098961
52536841962607931318942607902135379854764417926576982970794170722618316661902610
581990034084559568578220692451989237913208969760409593884604198504823784
*  cos(0.7) = 10 ^ -1 x 7.648421872844884262558599901918649092682105503737033560729
32458252065875043710163031201900052668332741177210958972173547364537654752068916
11893165525090317008240280866605450203793757586681896127993094652503134260055567
0138330427675719326757635363047487685702604513997374235057821451406443449
*  sin^2(0.7) + cos^2(0.7) - 1.0 = 10 ^ 0 x 0
