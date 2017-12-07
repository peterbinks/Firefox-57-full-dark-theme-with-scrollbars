<h1>Firefox 57+ full dark theme with dark scrollbars and multirow tabs/bookmarks</h1>

<p>This repository includes the files requires to (almost) fully dark theme firefox quantum to dark-gray colors 
(with #222-#444 colors mostly). </p>
<p><b>Of course... you could as well use these files to color your firefox any way you wanted</b>, the only thing you'd have to do
is change the correct values (what each class or id does is commented above each) in the .css files (as far as you know some 
basic css or color coding, it shouldn't be too hard)</p>
<p>What this "theme" will not affect will be your persona, the text color used by it, and the accent color (line above active tab). To change those settings, you can change them manually through the <code>about:config</code> page, searching 
<b>lightweightThemes.usedThemes</b> there, and changing the textcolor or accentcolor codes of your used persona respectively.</p>
<h3>Last update: <b>07/12/2017</b></h3>
<p>Files updated:</p>
<ul>
  <li><b>Userchrome.css</b> -> Changed the "done" button border color to a darker blue on the customization page.</li>
  <li><b>Usercontent.css</b> -> Changed all about: pages buttons to have a darker blue border. Added the theme to the <code>about:support</code> page.</li>
</ul>
<h3>Pre-Last update: <b>04/12/2017</b></h3>
<p>Files updated:</p>
<ul>
  <li><b>Userchrome.css</b> -> Added multirow support for the bookmarks toolbar (thanks to the code fixed by <b>jscher2000</b> in <a href="https://www.reddit.com/r/firefox/comments/75wya9/multiple_row_bookmark_toolbar_for_firefox_5758/">this reddit thread</a>) It won't be enabled by default, so you have to edit userchrome to use this feature. Also fixed some issue with Windows 8 close/min/resize buttons showing a bigger background with multirow tabs enabled.</li>
</ul>
<h3>Known issues:</h3>
<p><b>If you are using the method to change the scrollbars found here, you will have to edit the <code>chrome.manifest</code> file with each firefox update, since the update resets this file to become empty again</b> (which should at least give you one or two months before having to re-edit it).</p>
<p>I'm currently working on a way to make scrollbars change more permanent, but it may take some time... so you will still have to change the <code>chrome.manifest</code> manually until then.</p>
<h2>FAQ:</h2>
<p><b>Why use this method instead of using <a href="https://addons.mozilla.org/es/firefox/addon/styl-us/">Stylus</a>?</b></p>
<p>The main reason is that you can't style firefox about: pages nor the scrollbar with just stylus.</p>
<p><b>What features does this theme have?</b></p>
<p>The main features (apart from the theming) are:</p>
<ul>
  <li>Multiple row tabs.</li>
  <li>Multiple row bookmarks toolbar (2 usable rows by default, but it is NOT enabled by default. You can add more rows editing userchrome).</li>
  <li>Hides some rarely used commands on the context menu such as "Set image as desktop background".</li>
  <li>Changes the tab close button to always be visible.</li>
  <li>You can hide the sidebar completelly resizing it instead of having to click the sidebar button.</li>
  <li>Can change the URL bar font (You have to change the commented line on userchrome to use it).</li>
  <li>Can change the tabs position under the URL bar (You have to change the commented line on userchrome to use it).</li>
  <li>Change the Ublock Origin blocking page to a dark version (You need to change the commented line on usercontent).</li>
</ul>
<p>You can turn these features on or off changing the commented lines on the CSS file (To change them you just have to open the userchrome.css with notepad or any code editor, and encase between "/*" and "*/" (without the quotation marks) the lines you don't want to take effect)</p>

<h2>Installation</h2>

<h3>Main browser UI</h3>

<img src="https://i.imgur.com/dmIuudb.png" title="Dark firefox overall UI" />

<p>Most of the job is already done with the userContent.css and userChrome.css files that you have to place in the 
chrome folder of your firefox profile (Look below for "the chrome folder" section if you don't know where that is). For this to work as intended, you should be using a persona (aka lightweight theme) or the default dark theme (The persona used on the screenshot is "<a href="https://addons.mozilla.org/en-US/firefox/addon/deep-dark-blue-forest/">Deek Dark Blue forest</a>" by <b>Sondergaard</b>).</p>
<p>If you are only looking for how to change the default scrollbars, you can apply just that without the need
of using the usercontent or userchrome files provided here.</p>

<h3>The scrollbars</h3>
<p>The scrollbars file isn't as easy to install as userchrome or usercontent (but still pretty simple). 
The reason for this is that to style the scrollbars we can't use external styles through the stylus extension or userchrome.</p>
<p>To install the scrollbars, you will have to overwrite (or edit it, since it's just a line) a file (<code>chrome.manifest</code>), as well as <b>placing the scrollbars.css file inside firefox's root folder</b>.</p> 
<p><b>Since firefox resets the <code>chrome.manifest</code> file with each new update, you will have to change it each time firefox updates</b> (which should at least give you one or two months before having to re-edit it). I'll be trying to make a more permanent fix, but right now, this should be the fastest way to change the scrollbars.</p>

<p>Depending on your OS, the root folder will be in a different location (information taken from <a href="http://kb.mozillazine.org/Installation_directory">here</a>):</p>

<h4>For Windows, you can find firefox root folder here:</h4>
<code>32-bits Firefox -> C:\Program Files (x86)\Mozilla Firefox\</code>
<code>64-bits Firefox -> C:\Program Files\Mozilla Firefox\</code>
<br /><p>If you have a 32-bits Windows, you will only see the 64-bits path.</p>

<h4>For Linux, you can find firefox root folder here:</h4>
<code>32-bits Firefox -> 	/usr/lib/firefox-(version) -> For example, if using Firefox 57: /usr/lib/firefox-57.0</code>
<code>64-bits Firefox -> /usr/lib64/firefox-(version) -> F.ex, for Firefox 57: /usr/lib64/firefox-57.0</code>
<br /><p>The installation directory path may vary depending on the distribution if you use a package manager to install the application from their repository.</p>

<h4>For Mac, you can find firefox root folder here:</h4>
<code>/Applications/Firefox.app</code>
<br /><p>To open one of these folders, Ctrl-click it and select Show Package Contents. If you simply click it, you will start the application.</p>

<p>Once you have located the <code>chrome.manifest</code> file on firefox root folder (there is another one inside the "browser" folder that you don't have to edit), overwrite it with the <code>chrome.manifest</code> uploaded here.</p>
<p>If for some reason you wanted to edit it yourself, you can do so by editing it with notepad (or any code editor program you see fit for the job, but do NOT use Word or any other enriched text editor). You will see a blank file (it was 0kb heavy after all), where you should add the line:</p>

<code>override chrome://global/skin/scrollbars.css scrollbars.css</code>

<p>If you have done everything correctly, firefox should have the custom-made scrollbars now (or after you restart firefox if
you had it open).</p>
<h3>The chrome folder</h3>
<p>If you don't know where that is, just type <code>about:support</code> on the URL bar of your firefox, and in the page
you will be redirected to, on the section labed as "profile folder" click the <b>open folder</b> button.</p>
<p>After this, your profile folder will be open. You may or may not see the chrome folder. If you don't see it, just create it and place inside the usercontent.css and userchrome.css files.</p>

<p>If you want to know the exact location for profile folders (information taken from <a href="http://kb.mozillazine.org/Profile_folder_-_Firefox">here</a>):</p>

<h4>On Windows 7 and above, profile folders are in this location, by default:</h4>

<code>C:\Users\(Windows login/user name)\AppData\Roaming\Mozilla\Firefox\Profiles\(profile folder)</code>
  
<p>The AppData folder is a hidden folder; to show hidden folders, open a Windows Explorer window and choose "Tools → Folder Options → View (tab) → Show hidden files and folders".</p>

<p>You can also use this path to find the profile folder, even when it is hidden:</p>

<code>%APPDATA%\Mozilla\Firefox\Profiles\(profile folder)</code>

<h4>On Linux, profile folders are located in this other location:</h4>

<code>~/.mozilla/firefox/(profile folder)</code>

<p>The ".mozilla" folder is a hidden folder. To show hidden files in Nautilus (Gnome desktop's default file browser), choose "View -> Show Hidden Files".</p>

<h4>On Mac, profile folders are in one of these locations:</h4>

<code> ~/Library/Application Support/Firefox/Profiles/(profile folder)</code>
<code> ~/Library/Mozilla/Firefox/Profiles/(profile folder)</code>

<p>The tilde character (~) refers to the current user's Home folder, so ~/Library is the /Macintosh HD/Users/(username)/Library folder. For OS X 10.7 Lion and above, the ~/Library folder is hidden by default.</p>

<p>You can make them visible by typing the following in a terminal window.</p>
<code>defaults write com.apple.finder AppleShowAllFiles TRUE</code><br />
<code>killall Finder</code>
<br /><p>This will also cause any file icons to take on a hazy, 50% alpha look. To restore the old settings (hide the files and make the icons look normal) issue the same commands again, but enter FALSE instead of TRUE.<p>

<h2>The userChrome.css file</h2>

<p>The userchrome file turns dark all context menus, bookmarks, the url bar, the search bar, the main menu, and the toolbar. 
It will, although, not turn dark the extension popups you may have. <p>
<img src="https://i.imgur.com/wWjBcqz.png" title="Dark search menu (spanish)" />
<img src="https://i.imgur.com/7zj3SSq.png" title="Dark context menu (spanish)" />
<p>It will also turn dark the autocomplete popups (mostly a side-effect)</p>
<br />

<p>This userchrome will also make the close button on tabs always show, as well as adding multiple row tabs support thanks to <a href="https://github.com/andreicristianpetcu/UserChrome-Tweaks/blob/09fa38a304af88b685f4086bc8ea9997dd7db0fd/tabs/multi_row_tabs_firefox_v57.css">the code</a> of <b>Andreicristianpetcu</b>. It will also hide some (at least to me) useless options of the main context menu, such as "send image", 
"set as desktop background", "bookmark page", "send page", "bookmark this link", "send link" and "send tab/page/link to device".</p>
<p>If for some reason you wanted to keep any of those, you can still recover them deleting the css entries for the ones you are 
interested on (or commenting them between /* and */)</p>


<h2>The userContent.css file</h2>

<p>The usercontent file will turn dark the most commonly used <code>about</code> pages.</p>
<img src="https://i.imgur.com/e4zVTC7.png" title="Dark preferences page" /></a>
<p>These include:</p>
<ul>
  <li>Home</li>
  <li>Preferences</li>
  <li>Addons*</li>
  <li>About</li>
  <li>Error</li>
  <li>Cache</li>
  <li>Config</li>
  <li>Plugins</li>
  <li>Memory</li>
  <li>Downloads</li>
  <li>Debugging</li>
  <li>Support</li>
</ul>

<p>*The addons page has a popup (the one that appears when you right click an addon and choose "about...") that couldn't be
styled.</p>
<p>As of 24/11/2017, a dark theme for the Mozilla addons page was also added.</p>

<h2>The scrollbars.css file</h2>
<img src="https://i.imgur.com/2WBVmxY.png?1" title="Dark blue scrollbar" /></a>

<p>Same as with the other files, you can edit the scrollbars appearance using the scrollbars.css, editing only past the 
"New Scrollbar starts here" line. The reason for this is that to change the scrollbars we had to override the actual scrollbars
default file of the program, so you have to keep the original lines above your changes to prevent firefox from crashing (as
well as having a default scrollbar in case you wanted to play around with the new scrollbar attributes).</p> <br />
<h2>Credits</h2>
<p>The original code for the custom scrollbars belongs to <b>Arty2</b>, and you can find it <a href="https://gist.github.com/Arty2/fdf19aea2c601032410516f059d58eb1">here</a>.
<p>The original code for the multirow tabs was written by <b>Andreicristianpetcu</b>, and you can find it <a href="https://discourse.mozilla.org/t/tabs-in-two-or-more-rows-like-tabmixpro-in-quantum/21657/2">here</a>, or for just the code, <a href="https://github.com/andreicristianpetcu/UserChrome-Tweaks/blob/09fa38a304af88b685f4086bc8ea9997dd7db0fd/tabs/multi_row_tabs_firefox_v57.css">here</a>.
<p>The original code for the multirow bookmarks toolbar belongs to the original creator mentioned in <a href="https://www.reddit.com/r/firefox/comments/75wya9/multiple_row_bookmark_toolbar_for_firefox_5758/">this reddit thread</a>, whose code was fixed by <b>jscher2000</b> to use in our current firefox.
<p>Thanks to <b>BelladonnavGF</b> and <b>Hakerdefo</b> for noting some issues with the theme, and <b>BelladonnavGF</b> for the addition of the url font and and tabs below url bar suggestions.</p>
