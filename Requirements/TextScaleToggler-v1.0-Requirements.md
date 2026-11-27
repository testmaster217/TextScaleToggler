# Text Scale Toggler Requirements
> [!NOTE]
> All imformation in this document applies to a potential version 1.0 of this app. Requirements for later versions may be in separate documents, or may replace the contents of this one.

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
  * The product is architecturally simple enough that I don't expect any of these to be an issue, but as I keep stating, ease of use is the point of this thing. (Also accessibility, since this is an accessibility tool. In particular, its UI should not break in the same way as those of the apps and websites that inspired it, in addition to the product being screen-reader and keyboard navigable and have good color contrast (the WCAG's 4.5:1 should be good enough for me, and I would like to hit the 7:1 high contrast thing if Windows can change it to do that when a high-contrast theme is used, though maybe this won't be a problem with the default styling for all I know). Not sure what other accessibility things it might need.)
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
  * If the invalid value came from a saved preference, this should be reset to a default value and the user should be told that this happened in the same error message that complained about the value being invalid. (Since the GUI's slider for changing the value will probably get its initial value from this saved preference, this saved preference should also be reset (and error message about it displayed) if it is invalid when opening the GUI. In fact, it should be reset (and error message about it displayed) any time the program has to read or use it if it turns out to be invalid at that point.) The same thing should happen if the saved preferred text scale (or the file or setting where it's stored) is missing. (I imagine it being stored in a JSON file or something even though the registry would be more correct because I don't want to deal with the registry.)
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
* What do I mean by "saved preference" in an earlier answer?
  * I figured that the program would need some way to remember what you set the preferred text scale to the last time you used it so that you wouldn't have to provide it every time as the command line version currently requires. It should save this scale automatically whenever you change it. E.g. if you set the preferred text scale in the GUI, this new value will get saved automatically. Because of the backwards compatibility requirement, the command line will still need to allow you to specify a particular value, so that should override whatever's saved, but not change it. Also, the user should know that their preferred value was automatically saved, so the program should tell them that it has done so.
* Why do switching to 100% and switching to a preferred value have to use the same button/keystroke?
  * I think this would make it easy to switch between them. The two states (actual text scale = 100% and actual text scale = preferred value) are mutually exclusive, so making them the same button shouldn't hurt anything.
* What do I mean by "fully backwards compatible" with the command line version?
  * I mean that I should be able to type `textscaletoggler 175` (or whatever the name and preferred value are) into a terminal, and have it toggle between the given value and 100%. If the value is invalid, it should instead print an error message. There are a couple of changes that I want to make, though, so I guess it's not \_fully\_ backwards-compatible after all. Namely, giving the wrong number of arguments shouldn't necessarily be an error since more subcommands and things might be added in the future, and also I don't remember if the program's command name was ever changed from "toggletextscale" to "textscaletoggler", but I would like that to change if it hasn't, and finally, it currently switches to 100% instead of to the preferred value if the actual text scale is neither of them, and I want that to change.
* How should errors be displayed?
  * I imagine that if the user is using the GUI or the keyboard shortcut, the error message appears as a popup, while if they are using the command line, it will be printed to stderr.
* What should the default preferred text scale be?
  * It might as well be 175% (stored by the app as 175), since that's my preferred value.
* What if the app needs to reset or update the saved preferred text scale, but it can't write to the file (permission issue, file in use by another program, etc.)?
  * I don't expect this to happen in real life, but if it happens when trying to reset an invlaid value, the program should behave as normal, except that it should not try to reset the file, and the error message should tell the user why it couldn't. If it happens when trying to save the value, an error message should appear explaining what the problem is. Similar behavior to these two should happen in all cases where the program needs to read from/write to the file, but it can't.

### Revised Requirements
> [!NOTE]
> Low-priority and out-of-scope requirements don't get use cases.

* (TODO) Need to get feedback from actual potential users. Not sure how to do this.
* (H) Must be fully backwards-compatible with the existing (command-line-based) version. In particular, must be able to toggle between 100% and a preferred value by running the program from a terminal and giving a valid text scale value as the only command line argument.
* (H) Must be easy for non-technical users to use.
* (H) Must be able to toggle between 100% and a preferred value with a single button press/keyboard shortcut.
* (H) The keyboard shortcut must work even when the GUI is not open.
* (H) Fix terminal window popping up when I use the thing.
* (H) UI elements must not be cut off.
* (H) UI must be fully navigable via screen reader.
* (H) UI must be fully navigable via keyboard only.
* (H) UI must have color contrast of at least 4.5:1 and be able to reach 7:1 with a high-contrast Windows theme.
* (H) Must run on my version of Windows 11.
* (H) Must show the user an error message instead of changing anything when it tries to work with an invalid value. (An invalid value is anything other than an integer between 100 and 225, both inclusive.)
* (H) GUI slider to change the saved preferred text scale must be set to the existing saved preferred text scale when the GUI is opened.
* (H) Must reset saved preferred text scale to a default value (of 175%) if it is discovered to be invalid or missing, if the file where it's stored is missing, or if the section of the file where it's stored is missing, and must tell the user that it has done so. Namely, it must do this when the user toggles with the keyboard shortcut, as well as when the GUI opens.
* (H) Must automatically save preferred text scale whenever it is changed (and tell the user that it has done so) and must use this saved value when used (unless the user changes it again or specifies a different value via the legacy command line system (which does not change the saved value)).
* (H) Must display an appropriate error message if unable to function due to file access errors.
* (M) Must run on whatever versions of Windows are supported by Microsoft.
* (L) Must run on whatever version(s) of Windows 11 have the most users. (This may not matter due to the simplicity of the program and its interactions with the Windows APIs. Also, I can't seem to find the stats I'm looking for.)
* (L, Might be out of scope.) Command-line should have the same "--help" and "--version" options that are standard for command-line programs.
* (L, Might be out-of-scope.) Everything that can be done through the command line should be doable through the GUI/keyboard shortcut and vice versa.

### Use Cases
> [!NOTE]
> All use cases and user stories have been transferred to issues in the issue tracker at <https://github.com/users/testmaster217/projects/6/views/1>.
> 
> In all use cases in the issue tracker, "Participating Actors" sections and use case diagram have been omitted as the product only has one primary user, and this user is the only possible actor. Also, the "Goals" sections have been replaced with user stories, and new sections for acceptance criteria and tests have been added because I wanted to see if I could combine user stories with use cases.