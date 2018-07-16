unified hosts file with base extensions this repository consolidates several reputable hosts files and merges them into a unified hosts file with duplicates removed a variety of tailored hosts files are provided last updated july 10 2018 heres the raw hosts file with base extensions containing 62 089 entries logo by tobaloidee list of all hosts file variants the non github mirror is the link to use for some hosts file managers like hostsman for windows that dont work with github download links host file recipe readme raw hosts unique domains non github mirror unified hosts adware malware readme link 62 089 link unified hosts fakenews readme link 62 758 link unified hosts gambling readme link 63 706 link unified hosts porn readme link 72 169 link unified hosts social readme link 63 247 link unified hosts fakenews gambling readme link 64 375 link unified hosts fakenews porn readme link 72 838 link unified hosts fakenews social readme link 63 916 link unified hosts gambling porn readme link 73 786 link unified hosts gambling social readme link 64 864 link unified hosts porn social readme link 73 326 link unified hosts fakenews gambling porn readme link 74 455 link unified hosts fakenews gambling social readme link 65 533 link unified hosts fakenews porn social readme link 73 995 link unified hosts gambling porn social readme link 74 943 link unified hosts fakenews gambling porn social readme link 75 612 link expectation these unified hosts files should serve all devices regardless of os sources of hosts data unified in this variant updated hosts files from the following locations are always unified and included host file source description home page raw hosts update frequency license issues steven blacks ad hoc list additional sketch domains as i come across them link raw occasionally mit issues malware domain list malware domain list is a non commercial community project link raw weekly can be used for free by anyone issues add dead dead sites based on hostsfile org content link raw occasionally gplv3 issues add spam spam sites based on hostsfile org content link raw occasionally gplv3 issues dan pollock – someonewhocares how to make the internet not suck as much link raw frequently non commercial with attribution issues mvps hosts file the purpose of this site is to provide the user with a high quality custom hosts file link raw monthly cc by nc sa 4 0 issues yoyo org blocking with ad server and tracking server hostnames link raw frequently issues mitchell krogs badd boyz hosts sketchy domains and bad referrers from my nginx and apache bad bot and spam referrer blockers link raw weekly non commercial with attribution issues coinblocker simple lists that can help prevent cryptomining in the browser or other applications link raw frequently gplv3 issues lightswitch05 block ad and tracking domains link raw occasionally apache 2 0 issues uncheckyads windows installers ads sources sites based on https unchecky com content link raw occasionally issues add 2o7net 2o7net tracking sites based on hostsfile org content link raw occasionally gplv3 issues kadhosts fraud adware scam websites link raw frequently gplv3 issues adaway adaway is an open source ad blocker for android using the hosts file link raw occasionally cc by 3 0 issues add risk risk content sites based on hostsfile org content link raw occasionally gplv3 issues extensions the unified hosts file is extensible extensions are used to block domains by category extensions are optional and are added to the base hosts file extensions are combined in various ways wth the default hosts file and the combined products are stored in the alternates folder for example you may want to block porn domains in addition to the adware and malware we block by default that hosts file is stored in the porn subfolder of the alternates folder data for extensions is stored in the extensions folder you manage extensions by curating the extensions folder tree where you will find the data for fakenews social gambling and porn extension data that we maintain and provide for you generate your own unified hosts file note if you are using python 3 please install the dependencies with pip3 install user r requirements txt note if you are using python 2 please install the dependencies with pip2 install user r requirements python2 txt note we recommend the user flag which installs the required dependencies at the user level more information about it can be found on pip documentation to run unit tests in the top level directory just run python testupdatehostsfile py the updatehostsfile py script which is python 2 7 and python 3 compatible will generate a unified hosts file based on the sources in the local data subfolder the script will prompt you whether it should fetch updated versions from locations defined by the update json text file in each sources folder otherwise it will use the hosts file thats already there usage using python 3 python3 updatehostsfile py auto replace ip nnn nnn nnn nnn extensions ext1 ext2 ext3 using python 2 7 python updatehostsfile py auto replace ip nnn nnn nnn nnn extensions ext1 ext2 ext3 command line options help or h display help auto or a run the script without prompting when auto is invoked hosts data sources including extensions are updated no extensions are included by default use the extensions or e flag to include any you want your active hosts file is not replaced unless you include the replace flag backup or b make a backup of existing hosts file s as you generate over them extensions ext1 ext2 ext3 or e ext1 ext2 ext3 the names of subfolders below the extensions folder containing additional category specific hosts files to include in the amalgamation example extensions porn or e social porn flush dns cache or f skip the prompt for flushing the dns cache only active when replace is also active ip nnn nnn nnn nnn or i nnn nnn nnn nnn the ip address to use as the target default is 0 0 0 0 keepdomaincomments or k false default or true keep the comments that appear on the same line as domains the default is false since some router based implementations cant handle comments in line with hosts noupdate or n skip fetching updates from hosts data sources output subfolder or o subfolder place the generated source file in a subfolder if the subfolder does not exist it will be created replace or r trigger replacing your active hosts skipstatichosts or s false default or true omit the standard section at the top containing lines like 127 0 0 1 localhost this is useful for configuring proximate dns services on the local network compress or c false default or true compress the hosts file ignoring non necessary lines empty lines and comments and putting multiple domains in each line reducing the number of lines of the hosts file improves the performances under windows with dns client service enabled minimise or m false default or true like compress but puts each domain on a separate line this is necessary because many implementations of url blockers that rely on hosts files do not conform to the standard which allows multiple hosts on a single line how do i control which sources are unified add one or more additional sources each in a subfolder of the data folder and specify the url key in its update json file add one or more optional extensions which originate from subfolders of the extensions folder again the url in update json controls where this extension finds its updates create an optional blacklist file the contents of this file containing a listing of additional domains in hosts file format are appended to the unified hosts file during the update process a sample blacklist is included and may be modified as you desire note the blacklist is not tracked by git so any changes you make wont be overridden when you git pull this repo from origin in the future how do i include my own custom domain mappings if you have custom hosts records place them in file myhosts the contents of this file are prepended to the unified hosts file during the update process the myhosts file is not tracked by git so any changes you make wont be overridden when you git pull this repo from origin in the future how do i prevent domains from being included the domains you list in the whitelist file are excluded from the final hosts file the whitelist uses partial matching therefore if you whitelist google analytics com that domain and all its subdomains wont be merged into the final hosts file the whitelist is not tracked by git so any changes you make wont be overridden when you git pull this repo from origin in the future how can i contribute hosts records if you discover sketchy domains you feel should be included here here are some ways to contribute them option 1 contact one of our hosts sources the best way to get new domains included is to submit an issue to any of the data providers whose home pages are listed here this is best because once you submit new domains they will be curated and updated by the dedicated folks who maintain these sources option 2 add your domains to steven blacks personal data file fork this hosts this repo and add your links to https github com stevenblack hosts blob master data stevenblack hosts then submit a pull request warning this is less desireable than option 1 because the ongoing curation falls on us and what youve just done is created more work for us option 3 create your own hosts list as a repo on github if youre able to curate your own collection of sketchy domains then curate your own hosts list then signal the existance of your repo as a new issue and we may include your new repo into the collection of sources we pull whenever we create new versions what is a hosts file a hosts file named hosts with no file extension is a plain text file used by all operating systems to map hostnames to ip addresses in most operating systems the hosts file is preferential to dns therefore if a domain name is resolved by the hosts file the request never leaves your computer having a smart hosts file goes a long way towards blocking malware adware and other irritants for example to nullify requests to some doubleclick net servers adding these lines to your hosts file will do it block doubleclicks servers 0 0 0 0 ad ae doubleclick net 0 0 0 0 ad ar doubleclick net 0 0 0 0 ad at doubleclick net 0 0 0 0 ad au doubleclick net 0 0 0 0 ad be doubleclick net etc we recommend using 0 0 0 0 instead of 127 0 0 1 traditionally most host files use 127 0 0 1 the loopback address to establish an ip connection to the local machine we prefer to use 0 0 0 0 which is defined as a non routable meta address used to designate an invalid unknown or non applicable target using 0 0 0 0 is empirically faster possibly because theres no wait for a timeout resolution it also does not interfere with a web server that may be running on the local pc why not use just 0 instead of 0 0 0 0 we tried that using 0 doesnt work universally location of your hosts file to modify your current hosts file look for it in the following places and modify it with a text editor mac os x ios android linux etc hosts file windows systemroot \system32\drivers\etc\hosts file updating hosts file on windows on linux and mac os x you can simply run the python script but on windows more work is required due to compatibility issues in implementing some of the functionality for windows it is preferable to run the batch file as follows updatehostswindows bat this file must be run in command prompt with administrator privileges in the repository directory in addition to updating the hosts file it can also replace the existing hosts file and reload the dns cache it goes without saying that in order for this to work you must be connected to the internet to open a command prompt as administrator in the repositorys directory do the following windows xp start run cmd windows vista 7 start button type cmd right click command prompt run as administrator windows 8 start swipe up all apps windows system right click command prompt run as administrator windows 10 start button type cmd right click command prompt run as administrator you can also refer to the third party hosts managers section for further recommended solutions from third parties reloading hosts file your operating system will cache dns lookups you can either reboot or run the following commands to manually flush your dns cache once the new hosts file is in place the google chrome browser may require manually cleaning up its dns cache on chrome net internals dns page to thereafter see the changes in your hosts file see https superuser com questions 723703 windows open a command prompt with administrator privileges and run this command ipconfig flushdns if you want to use a huge hosts file by merging hphosts not included here you need to disable and stop dnscache service before you replace hosts file in windows systems you have been warned before flushing the dns cache open a command prompt with administrator privileges and run this command sc config dnscache start disabled sc stop dnscache linux open a terminal and run with root privileges debian ubuntu sudo etc rc d init d nscd restart linux mint sudo etc init d dns clean start linux with systemd sudo systemctl restart network service fedora linux sudo systemctl restart networkmanager service arch linux manjaro with network manager sudo systemctl restart networkmanager service arch linux manjaro with wicd sudo systemctl restart wicd service rhel centos sudo etc init d network restart others consult this wikipedia article mac os x open a terminal and run sudo dscacheutil flushcache sudo killall hup mdnsresponder release management this repository uses release it an excellent cli release tool for github repos and npm packages to automate creating releases this is why the package json and release it json files are bundled goals of this unified hosts file the goals of this repo are to automatically combine high quality lists of hosts provide easy extensions de dupe the resultant combined list and keep the resultant file reasonably sized a high quality source is defined here as one that is actively curated a hosts source should be frequently updated by its maintainers with both additions and removals the larger the hosts file the higher the level of curation is expected for example the huge hosts file from hosts file net is not included here because it is very large 780 000 entries and doesnt currently display a corresponding high level of curation activity it is expected that this unified hosts file will serve both desktop and mobile devices under a variety of operating systems third party hosts managers unified hosts autoupdate for windows the unified hosts autupdate package is purpose built for this unified hosts project as well as in active development by community members its sophisticated enough to allow any novice the ability to install and uninstall the blacklist of their choosing to their local hosts file and keep it automatically up to date while also being minimal enough to be able to be easily placed in a shared network location and deployed across an organization via group policies and since it is in active development by community members your bug reports feature requests and other feedback are most welcome interesting applications pi hole is a network wide dhcp server and ad blocker that runs on raspberry pi pi hole uses this repository as one of its sources this is a very interesting project to setup yourself or you can buy one pre loaded block ads and malware via local bind9 dns server for debian raspbian ubuntu set up a local dns server with a etc bind named conf blocked file sourced from here block ads malware and deploy parental controls via local dualserver dns dhcp server for bsd windows linux set up a blacklist for everyone on your network using the power of the unified hosts reformatted for dualserver and if youre on windows this project also maintains an update script to make updating dualservers blacklist even easier blocking ads and malwares with unbound – unbound is a validating recursive and caching dns resolver dnsmasq conversion script this github gist has a short shell script bash will work on any nix and uses wget awk present in most distros to fetch a specified hosts file and convert it the format required by dnsmasq supports ipv4 and ipv6 designed to be used as either a shell script or can be dropped into etc cron weekly or wherever suits script is short and easily edited also has a short document attached with notes on dnsmasq setup