# Text Scale Toggler Requirements

### Initial Requirements

* Must be fully backwards-compatible with the existing (command-line-based) version.
* Must be easy for non-technical users to use.
* Must be able to toggle between 100% and a preferred value with a single button press/keyboard shortcut.
* (Might be out of scope.) Command-line should have the same "--help" and "--version" options that are standard for command-line programs.
* (Might be out-of-scope.) Everything that can be done through the command line should be doable through the GUI/keyboard shortcut and vice versa.
* Fix terminal window popping up when I use the thing.



### Elicitation Question Answers

* What problem am I trying to solve?

  * Originally, I wanted to be able to switch Windows' text scale factor between 100% and my preferred value so that I could get around certain apps and websites breaking at the preferred value. Now that I've done that, I realize that other people might find this useful too, so I want to make a more user-friendly version (while maintaining backwards compatibility with the current version).
* What's the motivation for solving this problem?

  * I like to have Windows' text scale factor set to a high value because of my vision impairment, but I've found that this breaks a number of apps and websites, including several that I either use frequently, have had to use frequently in the past, or may have to use frequently in the future. Digging up the setting so I could change it temporarily whenever I use those apps and websites got annoying, so I made a script to change it more easily. After I made that script, I realized that a version that didn't require command-line knowledge could potentially be useful to other people, so I want to make that now.
* What would a highly successful solution do for me?

  * The existing (command-line-based) version of the program already does everything I personally need; I just thought that people who aren't comfortable with that might get some use out of it if there were more user-friendly ways to use it.
* What's a successful solution worth?

  * I don't actually plan on charging for this thing or making money from it at all. Not everything should have to be for-profit, and it's downright unjust that most accessibility software costs as much as it does.
* Who could influence this project?

  * It would be nice to get feedback from actual users, but I don't personally know anyone who maybe would use it.
* Who could be influenced by this project?

  * I don't see the project itself influencing anyone.
* Are there any related projects to this one?

  * No.
* Which activities should be included in the scope?

  * Everything that the program can currently do, but in a more user-friendly way than through a shell command.
* Could there be any unintended consequences of the new system?

  * Not that I can think of.
* What policies must the product conform to?

  * Nothing as far as I know.
* What goals could this product help me accomplish?

  * Working with apps/websites that aren't designed properly, see earlier answers.
* What problems do I expect this product to solve?

  * See earlier.
* What words would I use to describe this product?

  * "Effortless" and "simple" come to mind.
* What aspect of the product excites me?

  * The fact that I no longer have to open Settings, dig up the slider, change it, apply, wait for Windows to refresh, and then do it all again when I'm done with whatever thing I needed to change it for.
* What aspects are most/least valuable to the users?

  * I don't think I can answer this question well since I am the only user I know of, and the product already does everything *I* need, I just thought making it more user-friendly would help other people find it as useful as I do.
* What qualities (e.g., efficiency, security, reliability, etc.) are critical for the specific parts of the product?

  * The product is architecturally simple enough that I don't expect any of these to be an issue, but as I keep stating, ease of use is the point of this thing. (Also accessibility, since this is an accessibility tool. In particular, its UI should not break in the same way as those of the apps and websites that inspired it.)
* What events must the product respond to?

  * I imagine that one way people will use it is with a keyboard shortcut to do the toggling -- and this should trigger the toggling even when the program appears not to be running as a non-technical user would understand it (i.e., when the UI is not on screen, when there is no taskbar icon, etc.).
* Can I describe the environment in which the product will be used?

  * Any PC running a version of Windows that Microsoft officially supports. At the very least, must support mine and whatever has the most users (as long as Microsoft itself supports it i.e. nothing older than Windows 11). (Other versions can be lower priority.)
* Would anyone ever want to have multiple preferred text scales?

  * That is a possibility I thought of, but I decided it was out of scope for this version of the thing. It could happen in a future version, though.
* Could \_\_\_\_ ever occur?

  * NOT SURE WHAT TO FILL IN THE BLANK WITH. THE APP IS TOO SIMPLE.
* What should happen if the user tries to switch to an invalid number or some other invalid value?

  * If the user tries to switch to something invalid, they should get an error message and nothing should change. The command line program already does this. (Valid values are integers between 100 and 225, both inclusive. All other values are invalid.)
* What's most important to me about the product?

  * The most important things to me are already covered by the existing version of the thing. This project is basically just an upgrade to it.
* How would I judge whether the product is a success?

  * If it does everything that it's supposed to do, in every case. It might be nice if people other than me actually used it too.
* How should the product be different from the way things are done now?

  * It's already good in every respect except user-friendliness. I imagine it would be much easier for non-technical people to use if it had a GUI (I imagine this being similar to the one for Windows Magnifier) and (as I referenced earlier) a keyboard shortcut.
* Is there anything else I should be asking?

  * Why is the terminal window thing important? Because a terminal window popping up is normally something you see malware doing, and I want my program not to look like that.
* Why is a GUI or a keyboard shortcut a good idea?

  * Because non-technical people aren't going to be comfortable with the terminal or with automation tools (which is what the current version of the product is designed to be used with), but they would be used to a GUI and -- if they are "power users" among this group -- maybe keyboard shortcuts. Getting feedback from actual potential users would be REALLY good for making sure that this thing meets its ease-of-use goals.
* Why do I want the backwards compatibility with the current version?

  * Because I already set up a system using it and I don't want to change it (though depending on how this thing is designed, I may end up simplifying that system).
* Why do I want the "--help" and "--version" flags?

  * Because they are standard. Pretty much every command has them, and I don't want to be weird.
* Why do I want feature parity between the command line and the other interfaces?

  * Because I see this as the 1.0 version of the program, and not having this feature parity (and not having the two standard command line flags) seem like the kinds of kinks that a 1.0 release shouldn't have.



### Final Requirements

* (H) Must be fully backwards-compatible with the existing (command-line-based) version.
* (H) Must be easy for non-technical users to use.
* (H) Must be able to toggle between 100% and a preferred value with a single button press/keyboard shortcut.
* (H) Fix terminal window popping up when I use the thing.
* (H) Must have no apparent accessibility issues.
* (H) Must run on my version of Windows 11.
* (H) Must run on whatever version(s) of Windows 11 have the most users.
* (H) Must show the user an error message instead of changing anything when it tries to work with an invalid value. (An invalid value is anything other than an integer between 100 and 225, both inclusive.)
* (M) Must run on whatever versions of Windows are supported by Microsoft.
* (M) (Might be out of scope.) Command-line should have the same "--help" and "--version" options that are standard for command-line programs.
* (M) (Might be out-of-scope.) Everything that can be done through the command line should be doable through the GUI/keyboard shortcut and vice versa.
* (M, TODO NOT REQ) Need to get feedback from actual potential users. Not sure how to do this.



