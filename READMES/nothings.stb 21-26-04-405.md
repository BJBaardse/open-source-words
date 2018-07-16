this file is automatically generated do not change it by hand stb single file public domain or mit licensed libraries for c c most libraries by stb except stb dxt by fabian ryg giesen stb image resize by jorge l vinobs rodriguez and stb sprintf by jeff roberts library lastest version category loc description stb vorbis c 1 14 audio 5462 decode ogg vorbis files from file memory to float 16 bit signed output stb image h 2 19 graphics 7462 image loading decoding from file memory jpg png tga bmp psd gif hdr pic stb truetype h 1 19 graphics 4853 parse decode and rasterize characters from truetype fonts stb image write h 1 09 graphics 1568 image writing to disk png tga bmp stb image resize h 0 95 graphics 2627 resize images larger smaller with good quality stb rect pack h 0 11 graphics 624 simple 2d rectangle packer with decent quality stb sprintf h 1 05 utility 1833 fast sprintf snprintf for c c stretchy buffer h 1 03 utility 262 typesafe dynamic array for c i e approximation to vector doesnt compile as c stb textedit h 1 12 user interface 1404 guts of a text editor for games etc implementing them from scratch stb voxel render h 0 85 3d graphics 3803 minecraft esque voxel rendering engine with many more features stb dxt h 1 08b 3d graphics 728 fabian ryg giesens real time dxt compressor stb perlin h 0 3 3d graphics 316 revised perlin noise 3d input 1d output stb easy font h 1 0 3d graphics 303 quick and dirty easy to deploy bitmap font for printing frame rate etc stb tilemap editor h 0 38 game dev 4172 embeddable tilemap editor stb herringbone wa 0 6 game dev 1220 herringbone wang tile map generator stb c lexer h 0 09 parsing 962 simplify writing parsers for c like languages stb divide h 0 91 math 419 more useful 32 bit modulus e g euclidean divide stb connected comp 0 95 misc 1045 incrementally compute reachability on grids stb h 2 31 misc 14405 helper functions for c mostly redundant in c basically authors personal stuff stb leakcheck h 0 4 misc 186 quick and dirty malloc free leak checking total libraries 20 total lines of c code 53654 faq whats the license these libraries are in the public domain you can do anything you want with them you have no legal obligation to do anything else although i appreciate attribution they are also licensed under the mit open source license if you have lawyers who are unhappy with public domain every source file includes an explicit dual license for you to choose from are there other single file public domain open source libraries with minimal dependencies out there yes if i wrap an stb library in a new library does the new library have to be public domain mit no because its public domain you can freely relicense it to whatever license your new library wants to be whats the deal with sse support in gcc based compilers stb image will either use sse2 if you compile with msse2 or will not use any simd at all rather than trying to detect the processor at runtime and handle it correctly as i understand it the approved path in gcc for runtime detection require you to use multiple source files one for each cpu configuration because stb image is a header file library that compiles in only one source file theres no approved way to build both an sse enabled and a non sse enabled variation while weve tried to work around it weve had multiple issues over the years due to specific versions of gcc breaking what were doing so weve given up on it see https github com nothings stb issues 280 and https github com nothings stb issues 410 for examples some of these libraries seem redundant to existing open source libraries are they better somehow generally theyre only better in that theyre easier to integrate easier to use and easier to release single file good api no attribution requirement they may be less featureful slower and or use more memory if youre already using an equivalent library theres probably no good reason to switch can i link directly to the table of stb libraries you can use this url to link directly to that list why do you list lines of code its a terrible metric just to give you some idea of the internal complexity of the library to help you manage your expectations or to let you know what youre getting into while not all the libraries are written in the same style theyre certainly similar styles and so comparisons between the libraries are probably still meaningful note though that the lines do include both the implementation the part that corresponds to a header file and the documentation why single file headers windows doesnt have standard directories where libraries live that makes deploying libraries in windows a lot more painful than open source developers on unix derivates generally realize it also makes library dependencies a lot worse in windows theres also a common problem in windows where a library was built against a different version of the runtime library which causes link conflicts and confusion shipping the libs as headers means you normally just compile them straight into your project without making libraries thus sidestepping that problem making them a single file makes it very easy to just drop them into a project that needs them of course you can still put them in a proper shared library tree if you want why not two files one a header and one an implementation the difference between 10 files and 9 files is not a big deal but the difference between 2 files and 1 file is a big deal you dont need to zip or tar the files up you dont have to remember to attach two files etc why stb is this something to do with set top boxes no they are just the initials for my name sean t barrett this was not chosen out of egomania but as a moderately sane way of namespacing the filenames and source function names will you add more image types to stb image h if people submit them i generally add them but the goal of stb image is less for applications like image viewer apps which need to support every type of image under the sun and more for things like games which can choose what images to use so i may decline to add them if theyre too rare or if the size of implementation vs apparent benefit is too low do you have any advice on how to create my own single file library yes https github com nothings stb blob master docs stb howto txt why public domain i prefer it over gpl lgpl bsd zlib etc for many reasons some of them are listed here https github com nothings stb blob master docs why public domain md why c primarily because i use c not c but it does also make it easier for other people to use them from other languages why not c99 stdint h declare anywhere etc i still use msvc 6 1998 as my ide because it has better human factors for me than later versions of msvc