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
* (L) Must run on whatever version(s) of Windows 11 have the most users. (This may not matter due to the simplicity of the program and its interactions with the Windows APIs. Also I can't seem to find the stats I'm looking for.)
* (L, Might be out of scope.) Command-line should have the same "--help" and "--version" options that are standard for command-line programs.
* (L, Might be out-of-scope.) Everything that can be done through the command line should be doable through the GUI/keyboard shortcut and vice versa.

### Use Cases
> [!NOTE]
> "Participating Actors" sections and use case diagram have been omitted as the product only has one primary user, and this user is the only possible actor.

> [!NOTE]
> The "Goals" sections have been replaced with user stories, and new sections for acceptance criteria and tests have been added because I wanted to see if I could combine user stories with use cases.

##### Toggling Using the GUI
###### User Story:
    As a low-vision user,
    I want to change Windows' text scale factor between 100% and my preferred value with a single button press,
    So that I can easily fix apps and websites whose UIs break at my preferred text scale while using my preferred scale whenever possible.

###### Triggers:
Use the toggle function from the GUI.

###### Pre-Conditions:
Actual text scale is anything other than preferred scale (for switching to preferred scale)/actual text scale is preferred scale (for switching to 100%), GUI is open, Preferred scale is provided through GUI option.

###### Post-Conditions:
Actual text scale matches preferred scale (for switching to preferred scale)/actual text scale matches 100% (for switching to 100%), Windows has applied the change.

###### Basic Flow:
1. User uses the toggle function.
2. Change in actual text scale is applied.

###### Alternate Flows:
None.

###### Exceptions:
The GUI can be designed such that providing an invalid value through it is impossible (e.g. the value can be provided via a slider that goes from 100 to 225), but it's still possible that the program may not be able to read from the file (e.g. permission issue), in which case an error message should appear telling the user what the problem is.

###### Qualities:
* Should take only one button press (assuming the preferred scale has already been set).
* Change takes effect in less than 1 second.

###### Acceptance Criteria and Test Steps:
> [!NOTE]
> Additional tests will be provided to test boundary conditions.

Actual text scale can be set to preferred value by clicking a button in the GUI if it isn't already set to that preferred value.
* Set the preferred text scale to any valid value other than the current actual text scale using the GUI.
* Click "Toggle" button in the GUI.
* Confirm actual text scale was changed to provided preferred value.

Actual text scale can be set to 100% by clicking the same GUI button as setting it to the preferred value if it is already set to that preferred value.
* Set the preferred text scale to the current actual text scale using the GUI.
* Click "Toggle" button in the GUI.
* Confirm actual text scale was changed to 100%.

Error message is displayed if the toggle function can't work because the file can't be read to.
* Change the permissions of the file so the program can't read it.
* Click the "Toggle' button in the GUI.
* Confirm error message is displayed.
* Confirm actual text scale was not changed.

##### Toggling Using a Keyboard Shortcut
###### User Story:
    As a low-vision user,
    I want to change Windows' text scale factor between 100% and my preferred value with a keyboard shortcut,
    So that I can easily fix apps and websites whose UIs break at my preferred text scale while using my preferred scale whenever possible.

###### Triggers:
Use the toggle function via the keyboard shortcut.

###### Pre-Conditions:
Actual text scale is anything other than preferred scale (for switching to preferred scale)/actual text scale is preferred scale (for switching to 100%), Preferred scale is provided through saved preference (making the user type the preferred scale out would make the process less effortless).

###### Post-Conditions:
Actual text scale matches preferred scale (for switching to preferred scale)/actual text scale matches 100% (for switching to 100%), Windows has applied the change.

###### Basic Flow:
1. User uses the toggle function.
2. Change in actual text scale is applied.

###### Alternate Flows:
None.

###### Exceptions:
Provided preferred text scale is invalid (anything other than an integer between 100 and 225, both inclusive) or missing, the file where it's stored is missing, or the section of the file where it's stored is missing. In this case, the saved preferred text scale should be reset to a default value (of 175%), an error message should be displayed (which also tells the user that the scale was reset), and the actual text scale should not change.

If the value can't be reset because the file can't be written to (permission issue, in use by a different program, etc.), a different error message should be displayed saying why the value couldn't be reset.

A similar error message should appear if the value toggle function doesn't work due to similar reasons.

###### Qualities:
* Change takes effect in less than 1 second.
* The keyboard shortcut should work even when the GUI is not open.

###### Acceptance Criteria and Test Steps:
> [!NOTE]
> Additional tests will be provided to test boundary conditions.

Actual text scale can be set to a saved preferred value by using a keyboard shortcut if it isn't already set to that value.
* Confirm that the actual text scale is not the saved preferred value.
* Use the keyboard shortcut.
* Confirm actual text scale was changed to the saved preferred value.

Actual text scale can be set to 100% by using a keyboard shortcut if it is already set to a saved preferred value.
* Confirm that the actual text scale matches the saved preferred value.
* Use the keyboard shortcut.
* Confirm actual text scale was changed to 100%.

The keyboard shortcut works even when the GUI is not open.
* Same tests as the two tests above, but ensure that the GUI is not open when running the tests.

An error message is displayed and saved preference is reset to a default value when trying to switch to a scale below 100.
* Provide a text scale below 100.
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when the saved preference can't be reset due to file access issues when trying to switch to a scale below 100.
* Provide a text scale below 100.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to switch to a scale above 225.
* Provide a text scale above 225.
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when the saved preference can't be reset due to file access issues when trying to switch to a scale above 225.
* Provide a text scale above.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to switch to a scale that is a decimal number.
* Provide a text scale that is a decimal number.
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when the saved preference can't be reset due to file access issues when trying to switch to a scale that is a decimal number.
* Provide a text scale that is a decimal number.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to switch to a "scale" that is not a number.
* Provide a text scale that is not a number (i.e. random text).
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when the saved preference can't be reset due to file access issues when trying to switch to a "scale" that is not a number.
* Provide a text scale that is not a number.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to toggle when the saved preferred text scale has a key but no value.
* Make the saved preferred text scale have no value.
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when saved preference can't be reset to default value due to file access issues when trying to toggle when the saved preferred text scale has a key but no value.
* Make the saved preferred text scale have no value.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to toggle when the file that stores the saved preferred text scale is missing the relevant key-value pair.
* Remove the key and value for the saved preferred text scale from the file where they are stored.
* Try to switch to it.
* Confirm correct error message is displayed.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when saved preference can't be reset to default value due to file access issues when trying to toggle when the file that stores the saved preferred text scale is missing the relevant key-value pair.
* Remove the key and value for the saved preferred text scale from the file where they are stored.
* Change the file's permissions so that the program can't write to it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm saved preference is not changed.
* Confirm actual text scale is not changed.

An error message is displayed and saved preference is reset to a default value when trying to toggle when the file that stores the saved preferred text scale is missing.
* Remove the file where the saved preferred text scale is stored.
* Try to use the togglew keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm file is re-created.
* Confirm saved preference is reset to default value of 175.
* Confirm actual text scale is not changed.

An error message is displayed when the toggle function does not work due to file access issues.
* Change the permissions of the file where the saved preferred text scale is stored so that the program can't read from it.
* Try to use the toggle keyboard shortcut.
* Confirm correct error message is displayed.
* Confirm actual text scale is not changed.

##### Toggling Using the Command Line
###### User Story:
    As a legacy user,
    I want to change Windows' text scale factor between 100% and my preferred value by typing the program's name followed by my preferred value into the command line,
    So that I don't have to change my systems that depend on the program working like this.

###### Triggers:
Use the toggle function from the command line.

###### Pre-Conditions:
Actual text scale is anything other than preferred scale (for switching to preferred scale)/actual text scale is preferred scale (for switching to 100%), Terminal is open.

###### Post-Conditions:
Actual text scale matches preferred scale (for switching to preferred scale)/actual text scale matches 100% (for switching to 100%), Windows has applied the change.

###### Basic Flow:
1. User uses the toggle function.
2. Change in actual text scale is applied.

###### Alternate Flows:
None.

###### Exceptions:
Provided preferred text scale is invalid (anything other than an integer between 100 and 225, both inclusive). In this case, an error message should be printed to stderr and the actual text scale should not change.

###### Qualities:
* Change takes effect in less than 1 second.

###### Acceptance Criteria and Test Steps
> [!NOTE]
> Additional tests will be provided to test boundary conditions.

Actual text scale can be set to preferred value by typing the program's name followed by the preferred value into the command line if it isn't already set to that preferred value.
* Confirm actual text scale is not the provided preferred value.
* Type the command and run it.
* Confirm actual text scale was changed to provided preferred value.

Actual text scale can be set to 100% by typing the program's name followed by the preferred value into the command line if it is already set to that preferred value.
* Confirm actual text scale matches the provided preferred value.
* Type the command and run it.
* Confirm actual text scale was changed to 100%.

An error message is printed to stderr when trying to switch to a scale below 100.
* Provide a text scale below 100.
* Try to switch to it.
* Confirm error message is printed to stderr.
* Confirm actual text scale was not changed.

An error message is printed to stderr when trying to switch to a scale above 225.
* Provide a text scale above 225.
* Try to switch to it.
* Confirm error message is printed to stderr.
* Confirm actual text scale was not changed.

An error message is printed to stderr when trying to switch to a scale that is a decimal number.
* Provide a text scale that is a decimal number.
* Try to switch to it.
* Confirm error message is printed to stderr.
* Confirm actual text scale was not changed.

An error message is printed to stderr when trying to switch to a "scale" that is not a number.
* Provide a text scale that is not a number (i.e. use random text).
* Try to switch to it.
* Confirm error message is printed to stderr.
* Confirm actual text scale was not changed.

##### Fix Terminal Window Popping Up
This is a bug fix. It does not get a use case.

##### Running on My Version of Windows
This issue is so simple that I felt it didn't need a use case. To test it, simply run all tests on my version of Windows and make sure they all pass.

##### Saving Preferred Scale via GUI
###### User Story:
    As a GUI user,
    I want the program to automatically save my preferred text scale when I change it,
    So that I don't have to provide it every time I want to use the program.

###### Triggers:
Change the preferred text scale via the GUI.

###### Pre-Conditions:
GUI is open.

###### Post-Conditions:
Saved preferred text scale matches what is shown in the GUI.

###### Basic Flow:
1. User sets the preferred text scale via the GUI.
2. Saved preferred scale is updated. File where it is stored is created if it doesn't exist.
3. Message appears showing that the change was saved.

###### Alternate Flows:
User manually edits/creates the file that contains the saved preferred text scale.

###### Exceptions:
Can't write to the file (permission issue, file in use by another program, etc.). In this case, an error message should be visible that says what the problem is.

###### Qualities:
* Saving takes less than 1 second.

###### Acceptance Criteria and Test Steps:
Preferred text scale is saved when changed via the GUI.
* Open the GUI.
* Set the preferred scale using the GUI.
* Confirm "Preference saved" message is displayed.
* Confirm saved preference is changed.

An error message is displayed if the saved preferred text scale can't be updated due to file access issues.
* Change the permissions of the file that stores the saved preferred text scale so that the program can't write to it.
* Try to change the preferred text scale using the GUI.
* Confirm error message is displayed.
* Confirm saved preference is not changed.

##### GUI Reflects Saved Preferred Text Scale When Opened
###### User Stories:
    As a user,
    I want the GUI slider to match the saved preferred text scale when the GUI opens,
    So that I know the preferred text scale is what it says it is.

###### Triggers:
User opens the GUI.

###### Pre-Conditions:
None. The saved preferred text scale doesn't even need to exist. (See "Exceptions" below.)

###### Post-Conditions:
GUI matches saved preferred text scale.

###### Basic Flow:
1. User opens the GUI.
2. Slider matches saved preferred text scale.

###### Alternate Flows:
None.

###### Exceptions:
Saved preferred text scale is missing or invalid, its file is missing, or the relevant section of the file is missing. In this case, should reset the saved preferred text scale to a default value of 175 (which the slider will match) and display an error message saying that it was reset.

If the value can't be reset because the program can't write to the file (permission issue, file in use by another progrsam, etc.), should display a different error message than normal saying why it couldn't reset the value.

If the program can't read the value in the first place due to similar file access issues, an error message should be displayed saying so.

###### Qualities:
* The entire process should take less than 1 second.

###### Acceptance Criteria and Test Steps:
> [!NOTE]
> Additional tests will be provided to test boundary conditions.

GUI slider reflects the saved preferred text scale when the gUI is opened.
* Open the GUI.
* Confirm that the slider's value is the same as the saved prefered text scale.

Saved preferred text scale is reset to default value of 175 and error message is displayed when the GUI is opened if it is below 100.
* Change the saved preferred text scale to be below 100 without using the GUI.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is reset to default value.
* Confirm slider matches saved preferred text scale.

Error message is displayed when the GUI is opened if saved preferred text scale is below 100 and cannot be reset due to file access issues.
* Change the saved preferred text scale to be below 100 without using the GUI.
* Change the file's permissions so that the program can't read from it.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is not changed.

Saved preferred text scale is reset to default value of 175 and error message is displayed when the GUI is opened if it is above 225.
* Change the saved preferred text scale to be above 225 without using the GUI.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is reset to default value.
* Confirm slider matches saved preferred text scale.

Error message is displayed when the GUI is opened if saved preferred text scale is above 225 and cannot be reset due to file access issues.
* Change the saved preferred text scale to be above 225 without using the GUI.
* Change the file's permissions so that the program can't read from it.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is not changed.

Saved preferred text scale is reset to default value of 175 and error message is displayed when the GUI is opened if it is a decimal number.
* Change the saved preferred text scale to be a decimal number without using the GUI.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is reset to default value.
* Confirm slider matches saved preferred text scale.

Error message is displayed when the GUI is opened if saved preferred text scale is a decimal number and cannot be reset due to file access issues.
* Change the saved preferred text scale to be a decimal number without using the GUI.
* Change the file's permissions so that the program can't read from it.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is not changed.

Saved preferred text scale is reset to default value of 175 and error message is displayed when the GUI is opened if it is not a number.
* Change the saved preferred text scale to be not a number (i.e. to be random text) without using the GUI.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is reset to default value.
* Confirm slider matches saved preferred text scale.

Error message is displayed when the GUI is opened if saved preferred text scale is not a number and cannot be reset due to file access issues.
* Change the saved preferred text scale to be not  a number without using the GUI.
* Change the file's permissions so that the program can't read from it.
* Open the GUI.
* Confirm correct error message is displayed.
* Confirm saved preferred text scale is not changed.

Error message is displayed when the GUI is opened if the program cna't read the saved preferred text scale due to file access issues.
* Change the file's permissions so that the program can't read from it.
* Open the GUI.
* Confirm correct error message is displayed.

##### UI Elements Are Not Cut Off
###### User Stories:
    As a low-vision user,
    I want the app's UI to not have parts of it be cut off or anything,
    So that the app doesn't have the issue that inspired it in the first place.

###### Triggers:
N/A.

###### Pre-Conditions:
N/A.

###### Post-Conditions:
N/A.

###### Basic Flow:
N/A.

###### Alternate Flows:
N/A.

###### Exceptions:
N/A.

###### Qualities:
N/A.

###### Acceptance Criteria and Test Steps:
> [!NOTE]
> Unlike with other acceptance criteria, boundary tests are included here.
The GUI does not have anything cut off at 100%
* Set the actual text scale to 100%.
* Open the GUI.
* Confirm no cut off elements.

The GUI does not have anything cut off at 175%
* Set the actual text scale to 175%.
* Open the GUI.
* Confirm no cut off elements.

The GUI does not have anything cut off at 225%
* Set the actual text scale to 225%.
* Open the GUI.
* Confirm no cut off elements.

##### UI Is Fully Usable via Screen reader.
###### User Stories:
    As a low-vision user,
    I want the program to be completely usable with a screen reader,
    So that I can use it with particularly bad vision.

###### Triggers:
N/A.

###### Pre-Conditions:
N/A.

###### Post-Conditions:
N/A.

###### Basic Flow:
N/A.

###### Alternate Flows:
N/A.

###### Exceptions:
N/A.

###### Qualities:
N/A.

###### Acceptance Criteria and Test Steps:
All important elements are reachable using screen reader naviogation, in a logical order.
* Turn on the screen reader.
* Open the GUI.
* Attempt to navigate to each important element.
* Confirm that each element is reached and read by the screen reader in a logical order.

The "Preferred Scale" slider's value is read when navigated to, and when changed. (May or may not work depending on the screen reader.)
* Turn on the screen reader.
* Open the GUI.
* Navigate to the slider.
* Confirm that the slider's current value is read by the screen reader.
* Change the value.
* Confirm that the new value is read by the screen reader.

The "Toggle" button is declared to be a button.
* Turn on the screen reader.
* Open the GUI.
* Navigate to the button.
* Confirm that the screen reader reads it as a button.

##### UI Is Fully Keyboard-Navigable.
###### User Stories:
    As a user who prefers keyboard navigation,
    I want the program to be completely usable with only the keyboard,
    So that I can navigate and use it more quickly.

###### Triggers:
N/A.

###### Pre-Conditions:
N/A.

###### Post-Conditions:
N/A.

###### Basic Flow:
N/A.

###### Alternate Flows:
N/A.

###### Exceptions:
N/A.

###### Qualities:
N/A.

###### Acceptance Criteria and Test Steps:
All controls ("Preferred Scale" slider and "Toggle" button, as of this writing) can be reached via keyboard navigation, and in a logical order.
* Open the GUI.
* Attempt to use keyboard navigation to "tab through" the UI controls.
* Confirm each control can be reached.

"Preferred Scale" slider value can be changed via keyboard when focused.
* Open the GUI.
* Keyboard navigate to the "Preferred Scale" slider.
* Attempt to chnage its value using only the keyboard.
* Confirm the value changes.

"Toggle" button can be activated using the keyboard when focused.
* Open the GUI.
* Ensure that preferred text scale and actual text scale are not both 100%.
* Keyboard navigate to the "Toggle" button.
* Attempt to activate it using only the keyboard.
* Confirm actual text scale was toggled.

##### UI Has Acceptable Color Contrast.
###### User Stories:
    As a user,
    I want all elements of the program's UI to have a color contrast of at least 4.5:1,
    So that I can read the labels and controls well enough to use them.

###### Triggers:
N/A.

###### Pre-Conditions:
N/A.

###### Post-Conditions:
N/A.

###### Basic Flow:
N/A.

###### Alternate Flows:
N/A.

###### Exceptions:
N/A.

###### Qualities:
N/A.

###### Acceptance Criteria and Test Steps:
Color contrast is at least 4.5:1 for all text and controls using default Windows themes.
* Open the GUI.
* Confirm all text and controls have the required color contrast.
* Repeat in each default Windows theme. (Light and dark.)

Color contrast is at least 7:1 for all text and controls using high-contrast Windows themes, if not default Windows themes.
* Set Windows to a high-contrast theme.
* Open the GUI.
* Confirm all text and controls have the required color contrast.
* Repeat in each high-contrast Windows theme.
* (Optional) Repeat in each default Windows theme. (Light and dark.)

##### Running on All Microsoft-Supported Versions of Windows 11.
This issue is so simple that I felt it didn't need a use case. To test it, simply run all tests on all versions of Windows that are in support according to the "Releases" table at <https://learn.microsoft.com/en-us/lifecycle/products/windows-11-home-and-pro> and make sure they all pass.
