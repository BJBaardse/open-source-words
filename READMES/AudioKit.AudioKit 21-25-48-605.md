audiokit v4 3 audiokit is an audio synthesis processing and analysis platform for ios macos and tvos this document serves as a one page introduction to audiokit but we have much more information available on the audiokit websites audiokitpro com audiokit io features news blog and highlighted apps developer documentation key concepts nodes operations taps nodes are interconnectable signal processing components each node has an output and usually some parameters if the nodes processes another signal the nodes will also have an input operations are similar to nodes except that they are signal processing components that exist inside of a single node operations can be used as parameters to other operations to create very complex results taps use nodes as their data source but do not redirect the audio signal away from the source nodes output into other nodes this allows a tap to be moved from node to node more freely and to be added after the audio signal path has started installation installation details are found in the frameworks readme file audiokit is also available via cocoapods place the following in your podfile pod audiokit 4 0 example code there are three hello world projects one for each of the apple platforms ios macos and tvos they play oscillators and display waveforms the examples rely on audiokits frameworks so you can either download precompiled frameworks or build them yourself for hello world you only need to understand a few lines of code code description var oscillator akoscillator create the sound generator audiokit output oscillator tell audiokit what to output audiokit start start up audiokit oscillator start start the oscillator oscillator frequency random in 220 880 set oscillator parameters oscillator stop stop the oscillator playgrounds playgrounds contain bite size examples of audiokit and serve as tutorials for many of audiokits core concepts and capabilities there are over 100 playgrounds which cover basic tutorials synthesis physical modeling file playback midi effects filters and analysis we provide all playgrounds as a macos project that is ready to run in xcode just download the audiokitplaygrounds zip file from our releases page https github com audiokit audiokit releases open and build the project and go to the playground pages to learn audiokits api in a fun way we have videos of most of the playgrounds in action so you dont need to run xcode to check them out just go to audiokit playground videos http audiokit io playgrounds playgrounds http audiokit io examples playgrounds jpg http audiokit io playgrounds ray wenderlichs audiokit tutorial check out the audiokit tutorial on the ray wenderlich site youll be taken on a fun and gentle journey through the framework via the history of sound synthesis and computer audio getting help here are three methods for getting support which are roughly listed in order of what you should try first post your problem to stackoverflow with the audiokit hashtag if you dont have a problem that you can post to stackoverflow you may post to our google group but it is a moderated list and prepare to be rejected if the moderator believes your question is better suited for stackoverflow most are if you are pretty sure the problem is not in your implementation but in audiokit itself you can open a github issue contributing code audiokit is always being improved by our core team and our users this is a rough outline of what were working on currently when you want to modify audiokit check out the develop branch as opposed to master make your changes and send us a pull request about us audiokit was created by aurelius prochazka who is your life line if you need help matthew fecher manages all of audiokits web sites and stephane peter is aures co admin and manages audiokits releases but there are many other important people in our family group description core team the biggest contributors to audiokit slack pro level developer chat group contact a core team member for an in invitation contributors a list of all people who have submitted code to audiokit google group app announcements and mailing list for all users contributors this project exists thanks to all the people who contribute contribute