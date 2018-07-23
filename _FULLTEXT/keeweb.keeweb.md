Free cross-platform password manager compatible with KeePass This webapp is a browser and desktop password manager compatible with KeePass databases. It doesnt require any server or additional resources. The app can run either in browser, or as a desktop app. Quick Links Apps: Web, Desktop Timeline: Release Notes, TODO On one page: Features, FAQ Website: keeweb.info Twitter: kee_web Status The app is already rather stable, so basic stuff should work. Project roadmap with planned features and approximate schedule is on TODO page. Self-hosting Everything you need to host this app on your server is any static file server. The app is a single HTML file + cache manifest (optionally; for offline access). You can download the latest distribution files from gh-pages branch. If you are using Docker: put your dh.pem, cert.pem, key.pem to /etc/nginx/external/ run this script: bash docker run --name keeweb -d -p 443:443 -p 80:80 -v $EXT_DIR:/etc/nginx/external/ antelle/keeweb To make Dropbox work in your self-hosted app, go to this Wiki page. Building The app can be built with grunt: grunt (html file will be in dist/). Desktop apps are built with grunt desktop. This works only in mac osx as it builds dmg; requires wine. To run Electron app without building installer, build the app with grunt and start in this way: bash $ grunt dev $ npm run-script electron For debug build: run grunt dev open http://localhost:8085/tmp Contributing Please, read contribution guidelines: for issues and for pull requests. For pull requests: branch is important! master is only for hotfixes, develop is for new features. Heres a list of issues which need help. Also you can help by translating KeeWeb to your language. Important notes for pull requests please branch from develop, not master dont edit translation files except base.json, they will be replaced Donations KeeWeb is not free to develop. It takes time, requires paid code signing certificates and domains. You can help the project or say "thank you" with this button: Please note: donation does not imply any type of service contract. License MIT