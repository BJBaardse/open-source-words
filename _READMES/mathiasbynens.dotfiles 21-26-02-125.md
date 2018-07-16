mathiass dotfiles installation warning if you want to give these dotfiles a try you should first fork this repository review the code and remove things you dont want or need dont blindly use my settings unless you know what that entails use at your own risk using git and the bootstrap script you can clone the repository wherever you want i like to keep it in projects dotfiles with dotfiles as a symlink the bootstrapper script will pull in the latest version and copy the files to your home folder bash git clone https github com mathiasbynens dotfiles git cd dotfiles source bootstrap sh to update cd into your local dotfiles repository and then bash source bootstrap sh alternatively to update while avoiding the confirmation prompt bash set f source bootstrap sh git free install to install these dotfiles without git bash cd curl l https github com mathiasbynens dotfiles tarball master tar xzv strip components 1 exclude readme md bootstrap sh osx license mit txt to update later on just run that command again specify the path if path exists it will be sourced along with the other files before any feature testing such as detecting which version of ls is being used takes place heres an example path file that adds usr local bin to the path bash export path usr local bin path add custom commands without creating a new fork if extra exists it will be sourced along with the other files you can use this to add a few custom commands without the need to fork this entire repository or to add commands you dont want to commit to a public repository my extra looks something like this bash git credentials not in the repository to prevent people from accidentally committing under my name git author name mathias bynens git committer name git author name git config global user name git author name git author email mathias mailinator com git committer email git author email git config global user email git author email you could also use extra to override settings functions and aliases from my dotfiles repository its probably better to fork this repository instead though sensible macos defaults when setting up a new mac you may want to set some sensible macos defaults bash macos install homebrew formulae when setting up a new mac you may want to install some common homebrew formulae after installing homebrew of course bash brew sh some of the functionality of these dotfiles depends on formulae installed by brew sh if you dont plan to run brew sh you should look carefully through the script and manually install any particularly important ones a good example is bash git completion the dotfiles use a special version from homebrew feedback suggestions improvements welcome author mathias bynens thanks to… ptb and his macos setup repository ben alman and his dotfiles repository cătălin mariș and his dotfiles repository gianni chiappetta for sharing his amazing collection of dotfiles jan moesen and his ancient bash profile shiny tilde repository lauri ‘lri ranta for sharing loads of hidden preferences matijs brinkhuis and his dotfiles repository nicolas gallagher and his dotfiles repository sindre sorhus tom ryder and his dotfiles repository kevin suttle and his dotfiles repository and macos defaults project which aims to provide better documentation for macos haralan dobrev anyone who contributed a patch or made a helpful suggestion