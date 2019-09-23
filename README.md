# Odd:Mac
Odd:Mac is going to be a shell script which automatic installs all the necessary software you use based on your needs to quickly turn a newly formated Mac into a truly awesome Bro environment for web & app development.
Most of the installments within the steps below are based on our experience of what software is being used within the industry and our opinion of what will be optimized for the Bros working with the Odd:Pub.

## Table of Content
* [Core Install](#core-install)
  * [Step 1](#step-1)
  * [Step 2](#step-2)
  * [Step 3](#step-3)
  * [Step 4](#step-4)
  * [Step 5](#step-5)
  * [Step 6](#step-6)
  * [Step 7](#step-7)
  * [Step 8](#step-8)
* [Recommended Install](#recommended-install)
  * [Video player](#video-player)
  * [Mindfulness, Productivity & System apps](#mindfulness-productivity-system-apps)
  * [Communication](#communications)
  * [Password Manager](#password-manager)
  * [Cloud Storage](#cloud-storage)
  * [FTP](#ftp)
* [Optional Install](#optional-install)
  * [Adobe Bundle](#adobe-bundle)
  * [Sketch](#sketchapp)
  * [Font Manager](#font-manager)
  * [IDE](#ide)
  * [Hard disk Manager](#hard-disk-manager)
* [Contributers](#contributers)
* [License](#license)

## Core Install
### Step 1
#### Apple development environment
* [XCode](https://developer.apple.com/xcode/)

Your go-to environment for iOS app development.
```
xcode-select --install
```

### Step 2
#### Software Package Manager
* [Homebrew](http://brew.sh)
* [Caskroom](https://caskroom.github.io)
* [Caskroom Fonts](https://github.com/caskroom/homebrew-fonts)

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

```
brew tap caskroom/cask
```

```
brew tap caskroom/fonts
```

Optional GUI client for Homebrew
* [Cakebrew](https://www.cakebrew.com)

```
brew cask install cakebrew
```

### Step 3
#### Terminal Emulator
A Bro Terminal emulator.
* [iTerm2](https://www.iterm2.com)

```
brew cask install iterm2
```

Install the following color scheme for the iTerm2 window to be like the cool Bros.
https://github.com/tomislav/osx-terminal.app-colors-solarized

Install one of these fonts and change (we like and recommend Inconsolata).
https://github.com/powerline/fonts


### Step 4
#### Shell
Get a terminal experience worthy of a Bro.
*  [Zsh](http://www.zsh.org)
*  [Oh-My-Zsh](http://ohmyz.sh)

```
brew install zsh zsh-completions
```

To activate these completions, add the following to your .zshrc:
```
fpath=(/usr/local/share/zsh-completions $fpath)
```

You may also need to force rebuild `zcompdump`:
```
rm -f ~/.zcompdump; compinit
```

Additionally, if you receive "zsh compinit: insecure directories" warnings when attempting
to load these completions, you may need to run this:
```
chmod go-w '/usr/local/share'
```

Install Oh-My-Zsh
```
sh -c “$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Add these plugins to .zshrc to enhance your terminal Bro experience even more.
```
plugins=(git git-extras git-flow colored-man colorize github virtualenv virtualenvwrapper pip python brew osx zsh-syntax-highlighting npm docker node atom sudo)
```

Open the .zshrc file in your homedirectory & change the default theme from: ZSH_THEME="robbyrussell" to:
```
ZSH_THEME="agnoster"
```

### Step 5
#### Node Version Manager, Node.js, Package Managers
* [Node Version Manager](https://github.com/creationix/nvm)
* [Node.js](https://nodejs.org/en/),
* [NPM](https://www.npmjs.com)
* [Yarn](https://yarnpkg.com)
* [Bower](https://bower.io)
* [Gulp](http://gulpjs.com)
* [Grunt](http://gruntjs.com)
* [Webpack](https://webpack.js.org)
* [Autoprefixer](https://autoprefixer.github.io)
* [PostCSS](http://postcss.org)
* [Less](http://lesscss.org)
* [Sass](http://sass-lang.com)
* [Stylus](http://stylus-lang.com)

Install Node Version Manager
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash
```

Add this lines to .zshrc
```
export NVM_DIR="/Users/jonasbroms/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
```

To download, compile, and install the latest release of node:
```
nvm install node
```

Install Yarn Package Manager
```
brew install yarn
```

Recommended packages to install globally:
```
bower
grunt
grunt-cli
gulp
gulp-cli
postcss
webpack
autoprefixer
less
sass
stylus
babel
```

### Step 6
#### Virtualization & Containerization
* [VirtualBox](https://www.virtualbox.org/)
* [Docker](https://www.docker.com)
* [Docker Machine](https://docs.docker.com/machine/)
* [Docker Compose](https://docs.docker.com/compose/)
* [Docker Swarm](https://docs.docker.com/swarm/)

```
brew cask install virtualbox
```

```
brew install docker docker-machine docker-compose docker-swarm
```

Recommended images to install for Docker:
```
docker pull node php mariadb python ruby alpine nginx mongo httpd busybox debian java mysql centos redis
```

Optional images to install:
```
docker pull vagrant composer drupal wordpress joomla
```

### Step 7
#### Web browsers
* [Google Chrome](https://www.google.com/chrome)
* [Mozilla Firefox](https://www.mozilla.org/firefox/)
* [Opera](http://www.opera.com)
* [Tor](https://www.torproject.org/)

```
brew cask install firefox google-chrome opera torbrowser
```

### Step 8
#### Texteditor & plugins
* [Sublimetext](https://www.sublimetext.com)
* [Atom.io](https://atom.io)
* [Textmate](https://macromates.com)
* [Macvim](http://macvim-dev.github.io/macvim/)

Choose a Texteditor that you think is Bro worthy

```
brew cask install sublime
```

or

```
brew cask install atom
```

or
```
brew cask install textmate
```

```
brew cask install macvim
```

Depending on Texteditor, please install following packages by first:
For Atom.io
```
apm install
```

For Sublimetext
```
subl install
```

Packages
```
dash atom-material-ui monokai editorconfig emmet file-icons language-babel language-docker language-gitattributes language-gitignore language-htaccess language-gfm language-mongodb language-php language-xml language-sql language-svg language-mjml language-sass language-jsont language-dots minimap linter linter-less linter-docker linter-htmlhint linter-eslint linter-jshint linter-jsonlint pigments react react-es6-snippets
atom-react-native-css atom-storybook
```

## Recommended Install
-------------------------
### Video player
```
brew cask install vlc
```

### Mindfulness, Productivity & System apps
Makes the color of your computer's display adapt to the time of day, deduct unimportant information in top navbar, organize windows & optimize your workflow with easy access thru smart keyboards shortcuts.
* [Alfred](resolutionator)
* [Bartender](https://www.macbartender.com)
* [Spectacle](https://www.spectacleapp.com)
* [f.lux](https://justgetflux.com)
* [Resolutionator](https://manytricks.com/resolutionator/)
* [Dash](https://kapeli.com/dash)
* [Clip Menu](http://www.clipmenu.com/)
* [The Unarchiver](http://unarchiver.c3.cx/unarchiver)

```
brew cask install spectacle alfred bartender resolutionator flux dash clipmenu the-unarchiver
```

And install these Dash docsets for easy & offline access to all the necessary programming documentation used in Bro:Pform :
```
dash-install://repo_name=Cocoa Docsets&entry_name=AFNetworking
bash
Apache HTTP Server
Javascript
Webpack
React
CSS
HTML
SVG
Node.js
Docker
```

### Communication
Communicate with your Sis & Bros.
* [Skype](https://www.skype.com/)
* [Slack](https://slack.com)
* [Textual](https://www.codeux.com/textual/)
* [Irssi](https://irssi.org)

```
brew cask install skype
```

and/or

```
brew cask install slack
```

and/or

```
brew cask install textual
```

or

```
brew cask install irssi
```

### Password Manager
* [lastpass](https://www.lastpass.com)
* [1password](https://1password.com)
```
brew cask install lastpass
```

or

```
brew cask install 1password
```

### Cloud storage
* [Google Drive](https://www.google.com/drive/)
* [Dropbox](https://www.dropbox.com)
```
brew cask install google-drive
```

and/or

```
brew cask install dropbox
```

### FTP
* [Transmit](https://panic.com/transmit/)
* [Filezilla](https://filezilla-project.org)
* [Cyberduck](https://cyberduck.io)
```
brew cask install transmit
```

or

```
brew cask install filezilla
```

or

```
brew cask install cyberduck
```


## Optional Install
-------------------------
### Adobe Bundle
* [Adobe Photoshop](http://www.adobe.com/products/photoshop.html)
* [Adobe Lightroom](http://www.adobe.com/products/photoshop-lightroom.html)
* [Adobe Bridge](http://www.adobe.com/products/bridge.html)
* [Adobe InDesign](http://www.adobe.com/products/indesign.html)
* [Adobe Illustrator](http://www.adobe.com/products/illustrator.html)
* [Adobe Creative Cloud](http://www.adobe.com/creativecloud.html)

```
brew cask install adobe-illustrator-cc adobe-photoshop-cc adobe-creative-cloud adobe-photoshop-lightroom adobe-bridge-cc adobe-indesign-cc
```

### Sketch
* [Sketch](https://sketchapp.com)
* [Sketch-toolbox](http://sketchtoolbox.com)

```
brew cask install sketch sketch-toolbox
```

Install these handy plugins for Sketch thru Sketch-Toolbox GUI
* [Renameit](https://github.com/rodi01/RenameIt)
* [CSSketch](https://github.com/JohnCoates/CSSketch)
* [Blade](https://github.com/sskyy/blade)
* [Sketch Iconfont](https://github.com/keremciu/sketch-iconfont)

### Font Manager
* [Skyfonts](https://skyfonts.com)
* [RightFont](https://rightfontapp.com)

```
brew cask install skyfonts
```

```
open /usr/local/Caskroom/skyfonts/5.7.1.0/SkyFonts.app
```

or

```
brew cask install rightfont
```

### IDE
* [Webstorm](https://www.jetbrains.com/webstorm/)
* [IntelliJ IDEA](https://www.jetbrains.com/idea/)
* [Coda 2](https://panic.com/coda/)

```
brew cask install webstorm
```

or

```
brew cask install intellij-idea
```

or

```
brew cask install coda
```

### Hard disk Manager
* [Daisy](http://www.daisydiskapp.com)

```
brew cask install daisydisk
```

### Git Client
* [Github Desktop](https://desktop.github.com)
* [Tower](https://www.git-tower.com/)

```
brew cask install github-desktop
```

or

```
brew cask install tower
```

### Fonts
#### General
* [Font](#)
* [Font](#)
* [Font](#)
* [Font](#)
* [Font](#)

```
brew cask install font-menlo font-montserrat font-raleway font-merriweather font-lato font-open-sans font-roboto
```

#### System/Web Development
* [Fira-Code](https://github.com/tonsky/FiraCode)
* [Inconsolata](https://fonts.google.com/specimen/Inconsolata)
* [Hack](http://sourcefoundry.org/hack/)
* [Source Code Pro](http://adobe-fonts.github.io/source-code-pro/)

```
brew cask install font-menlo-for-powerline font-inconsolata font-consolas-for-powerline font-hack font-source-code-pro
```

## Contributers
* [Jonas Bröms]()
* [Olle Bröms]()

## License
