# PromptKit

PromptKit is an advanced dialog engine for Shortcuts and iOS. PromptKit creates powerful, interactive, multilingual, and multi-step prompts featuring speech, dictation, menus, dialogs, and automatic language translation. 

For shortcut developers, the [PromptKit API](#developer) facilitates the creation of interactive prompts with branching logic, input validation, history, state, external shortcut support, and data storage, all without writing a single line of code. 

Finally, PromptKit Stories combine multiple prompts together to create interactive guides, decision trees, adventure books for children, and improved Siri assistant-like functionality. 

- [**Download PromptKit From RoutineHub**](https://routinehub.co/shortcut/2583)

![PromptKit](https://adamtow.github.io/promptkit/images/promptkit-hero.png)

## Table of Contents
- [Benefits](#benefits)
	- [User Benefits](#user-benefits)
	- [Developer Benefits](#developer-benefits)
	- [PromptKit Stories](#stories)
- [Getting Started](#getting-started)
- [Using PromptKit](#using-promptkit)
- [Exploring PromptKit](#interface)
- [Settings](#settings)
- [PromptKit API](#developer)
- [Localization](#localization)
- [App Framework](#app-framework)
- [Troubleshooting](#troubleshooting)
- [License](#license)

****

<span id="benefits"></span> 
## PromptKit Benefits
PromptKit serves both end-users and developers alike.

<span id="user-benefits"></span>
Users of shortcuts whose prompts are powered by PromptKit gain the ability to:

- Input information using the keyboard or by voice.
- Automatically translate messages and prompts to over 25 languages.
- Experience and enjoy rich, data-driven flows with PromptKit Stories.
- Work exclusively with voice or dialog-driven prompts. If offline, voice-driven prompts will switch to dialog-driven prompts.

![PromptKit Prompt Formats](https://adamtow.github.io/promptkit/images/prompt-format.png)

<span id="developer-benefits"></span>
PromptKit allows developers to: 

- Create single and multi-step prompts that can validate user input without having to write any code. 
- Choose from an extensive list of prompt types, including:
	- Alert
	- Confirm
	- Date
	- Date and Time
	- HTML
	- List
	- Markdown
	- Notification
	- Number
	- Quick Look
	- Result
	- Speak
	- Text
	- Time
	- URL

![PromptKit Tester](https://adamtow.github.io/promptkit/images/promptkit-tester.png)

- Restrict prompts to accept a list of answers. Each answer can have multiple alternate responses.
- Validate user input with operators such as:
	- contains
	- equals
	- exact equality
	- greater than
	- less than
	- between
	- before
	- after
	- between
- Repeat the prompt once or multiple times if the input is not validated.
- Change the message or input method for each prompt repetition. 
- Access every response the user provided or just the final response.
- Detect and return user cancelled 🛑, no response ❓, and successful responses by the user.
- And [much more](#developer)!

<span id="stories"></span>
### PromptKit Stories

PromptKit Prompts can be bundled together as scenes of a PromptKit Story. Stories extends the power of PromptKit by creating rich, interactive, multilingual, multi-step, and branching experiences. Stories can also call external shortcuts which can interact with other PromptKit scenes. 

Stories make it easy to write:

- Tutorial shortcuts.
- Decision based stories for kids and adults.
- Assistant-style shortcuts that have state, understand context, and feature multiple steps.
- Universal translator from one language to another.

Developing a PromptKit Prompt is as easy as sending PromptKit a text string or a dictionary object. [Learn more about its API](#developer) to unlock its full potential, including the ability to:

- Send and receive data from external shortcuts. 
- Store and share data between story scenes. 
- Access a history of past prompts (i.e. go back to step 4 or start over from the beginning).

****

<span id="getting-started"></span>
## Getting Started
Get started by downloading and installing PromptKit. The latest version is available on RoutineHub:

<span id="download"></span> 
- [**Download PromptKit**](https://routinehub.co/shortcut/2583)

After installing, run PromptKit from the Shortcuts Home screen. It's a large shortcut with over 3500 actions, so it will take a long time to run from the Edit Shortcut Screen. 

### Setup Assistant

The first time you run PromptKit, the setup assistant will walk you through the steps of configuring the shortcut. Each of the menus and prompts you see in the assistant are
built using [PromptKit's easy-to-use API](#developer).

![PromptKit Setup #1](https://adamtow.github.io/promptkit/images/setup-1.png)

![PromptKit Setup #2](https://adamtow.github.io/promptkit/images/setup-2.png)

![PromptKit Setup #3](https://adamtow.github.io/promptkit/images/setup-3.png)

You will configure and learn about:

- **Check for Updates**: Configure PromptKit to check for updates automatically at startup of the main application.
- [**Detect Languages**](#detect-languages): Determine the language of a prompt so PromptKit can provide these benefits to you:
	- [**Auto Translate**](#auto-translate): Set PromptKit to translate prompts from one language to another. Choose from over 25 supported languages. 
	- [**Translation Dictation**](#translation-dictation): For prompts that employ dictation, this setting allows you to dictate your response in the translated language. If a prompt was originally written to English and you are translating to French, you can respond back in French. 
- [**Default Mode**](#default-mode): for prompts that don't specify a mode of operation (i.e. dialog or voice driven prompts), PromptKit will use the setting you choose here. 
- [**Mode Override**](#mode-override): PromptKit allows the user to override all modes and use just one way to interact with PromptKit Prompts. 
- [**Ask Story Mode**](#ask-story-mode): When starting a PromptKit Story, PromptKit can run a story temporarily in a given mode. 

Once setup is complete, you can [find more PromptKit compatible shortcuts](https://routinehub.co/search/?q=PromptKit) on RoutineHub, read this documentation, or go to the [PromptKit Home screen](#interface). 

****

<span id="using-promptkit"></span>
## Using PromptKit

Once you've installed and set up PromptKit, you'll want to test it out. You can either download the PromptKit Tester shortcut or look for PromptKit-aware shortcuts or PromptKit Stories on RoutineHub:

- [PromptKit Tester](https://routinehub.co/shortcut/2628), a shortcut that showcases the ways PromptKit can present and request information.
- [PromptKit-Aware Shortcuts](https://routinehub.co/search/?q=PromptKit)
- [PromptKit Stories on RoutineHub](https://routinehub.co/search/?q=PKS)

Opening the PromptKit Tester shortcut, for instance, will show you a list of Prompt types supported by PromptKit.

![PromptKit Tester](https://adamtow.github.io/promptkit/images/promptkit-tester.png)

****

<span id="interface"></span>
## Exploring PromptKit
PromptKit is typically run from other shortcuts. You would launch PromptKit from the Shortcuts Home if you want to adjust its settings or access PromptKit Stories you have installed. 

Here is an overview of the menu items you will see in the PromptKit Home screen. 

![PromptKit Screens](https://adamtow.github.io/promptkit/images/promptkit-screens.png)

### Run Controls

These two menu items give you access to your PromptKit Stories or to testing prompts that you write in JSON or text.

#### Run PromptKit Story
Searches for and displays any shortcut that contains "PKS" in your library. Tapping on an entry runs the shortcut. You can also tap the Find menu item to search for more PromptKit-award shortcuts on RoutineHub.

#### Run from Text File
Displays a text Input dialog where you can copy and paste text that will be interpreted as either a PromptKit Prompt or a PromptKit Story. 

![Ways to run PromptKit: From a shortcut, Shortcuts Home, PromptKit's Run a PromptKit Story Shortcut, and PromptKit's Run from Text File](https://adamtow.github.io/promptkit/images/ways-to-run-promptkit.png)

### Mode Controls

<span id="default-mode"></span>
#### Default Mode
If a PromptKit Prompt does not specify a mode to use, it will adopt what you choose in this setting.

- **Use Dialogs**: Displays dialogs, alerts, and menus to display information and ask for user input. 
- **Use Speech and Dialogs**: Speaks information to be displayed to the user, followed by prompting for user input via dialogs and menus. 
- **Use Speech and Dictation**: Speaks information to be displayed to the user and employs dictation to capture user input. 

<span id="mode-override"></span>
#### Override Mode
This setting forces PromptKit Prompts and Stories to use one of the three modes listed above, regardless of the mode setting in the either the Prompt or Story.

> Note: Prompts can still set the `allowModeOverride` setting to false to prevent Mode Override .

Mode Override lets the user control exactly how they want to receive and interact with Prompts and Stories on their iOS devices. For developers, overriding the mode makes it easy to test how their Prompts and Stories work across all three modes. 

If you leave Mode Override disabled, Prompts and Stories will be able to switch freely between using dialogs, speech with dialogs and speech with dictation. 

<span id="ask-story-mode"></span>
#### Ask Story Mode
This setting prompts you to choose a mode before running a PromptKit Story. It is only available when Mode Override is disabled. It effectively functions as a temporary Mode Override setting for Stories. 

![Ask Story Mode](https://adamtow.github.io/promptkit/images/ask-story-mode.png)

> Note: Individual Prompts can still override both Mode Override and Ask Story Mode by setting the `allowModeOverride` to false.

### Translation

This section unlocks the ability to automatically translate prompts from one language to another. 

<span id="detect-languages"></span>
#### Detect Languages 
If you encounter a prompt in another language that does not specify a spoken language, this setting allows PromptKit to detect the language via the Detect Language Action in Shortcuts. This feature is powered by Microsoft Cognitive Services. 

> NOTE: Currently all translation features require a connection to the internet. If your network connection is slow, you may experience slowdowns and  difficulties running Prompts and Stories. Should this occur, disable Detect Languages. 

If your internet connection is off, dictation will be disabled and prompts will run in either manual or manual with speech mode. 

![Translation Settings](https://adamtow.github.io/promptkit/images/translation-settings.png)


<span id="auto-translate"></span>
#### Auto Translate

Turn on this setting to automatically convert prompts and messages from one language to another. 

Suppose you speak French. Setting the Translation Language to French and turning on Auto Translate will translate any Prompt that does not directly specify its spoken or dictation language to French.

> A Prompt that lists out its spoken language or dictation language will use specified language, not the translated language. Prompt messages are still translated but spoken messages and user input remain in the specified language. 

<span id="translation-language"></span>
#### Translation Language 

PromptKit currently supports 25 languages:

- Arabic
- Cantonese (Traditional)
- Chinese Traditional
- Chinese Simplified
- Czech
- Danish
- Dutch
- English
- Finnish
- French
- German
- Greek
- Hebrew
- Hindi
- Hungarian
- Indonesian
- Italian
- Japanese
- Korean
- Norwegian
- Polish
- Portuguese
- Romanian
- Russian
- Slovak
- Spanish
- Swedish
- Thai
- Turkish

PromptKit uses the Translate Text with Microsoft action to convert from one language to another. It require an active internet connection to work. 

> If you are a native speaker of any of these languages, help make PromptKit more accurate by contributing to improving a language dictionary. See the [developer section on language dictionaries](#language-dictionary) for more information. 

<span id="translation-dictation"></span>
#### Allow Translation Dictation
This setting allows the user to use dictation with translated Prompts. When disabled, dictation is turned off for those Prompts that require a specific response. 

This is because of several reasons:

1. The responses are not able to be translated to another language. This is common for proper names or technical terms. 
2. Responses are incorrectly translated by the Translate Text with Microsoft action. 
3. The user can not speak the translation language and cannot get past the prompt. 

Developers of Prompts and Stories can follow several [best practice](#best-practices)s to assist users who may have Translation Dictation enabled.

<span id="display-original-message"></span>
#### Display Original Message
When enabled, this option displays the original message alongside the translated version. Disable it to only show the translated version in prompts, dialogs, alerts and notifications. 

### PromptKit

- **About**: Displays the PromptKit About dialog. Shows the current version and build number. 
- **Donate**: Enjoy using PromptKit? Consider making a [donation](https://paypal.me/adamtow) to support its future development. 
- **Help**: Displays the documentation you are reading now. 
- **Settings**: Opens the [PromptKit Settings](#settings) page. 

****

<span id="settings"></span>
## PromptKit Settings
PromptKit is highly configurable from the PromptKit Home screen, but there are a few more tweaks you can make to its operation from the Settings page.

![Settings and Lock Detection](https://adamtow.github.io/promptkit/images/lock-detection.png)

- **Default Prompt Repetitions**: For Prompts that do not specify a `repeat` attribute, this is the number of times a Prompt will repeat before returning the ❓ response value. 
- **Check for Updates Automatically**: Check for updates to PromptKit whenever  you launch PromptKit from the Shortcuts Home screen. Requires an internet connection for this to work. This does not affect the speed at which PromptKit runs when evaluating prompts. 
- **Lock Detection**: If you use PromptKit with [Cronios, the shortcuts scheduler for iOS](http://cronios.com), you can alert the user before displaying a Prompt if it [detects that the device may be locked](#lock-detection). 
	- **Unlock Prompt**: Change what is spoken to you when PromptKit is running in the background when the screen is off.  
- **Debug Level**: For developers, enable this and set a level of alerting to see how your Prompts and Stories are being interpreted by PromptKit. 
- **Check for Updates**: Manually check to see if there is an update PromptKit on RoutineHub. 
- **Change Language**: Change the PromptKit application language. Visit the section on localizing PromptKit if [you want to see PromptKit localized in your language](localization). 
- **Run Setup Assistant**: Re-runs the assistant that you used when you first installed PromptKit. 

<span id="lock-detection"></span> 
### Lock Detection
If you are running PromptKit-aware shortcuts in the background with [Cronios, the shortcuts scheduler for iOS](http://cronios.com), you will want to have this setting enabled. 

The shortcut will check if the device may be off by inspecting the brightness value of the screen. If it's 0, it's likely that the device is off and locked. It will then audible alert the user to unlock the device before displaying the Prompt. 

> NOTE: PromptKit can not determine if the device is locked if the screen is on. PromptKit will try to display the Prompt but will error out, terminating any shortcuts that may have been running in the background like Cronios. 

To change the unlock prompt, tap Unlock Prompt from the Settings screen. The language that will be used is your system language and will not be translated by PromptKit.

****

<span id="developer"></span>
## Developing for PromptKit

Whether you are making a simple or complex, interactive, multilingual, and multi-step prompt, the process of creating a PromptKit Prompt is very easy. 

- [PromptKit Prompt Format](#prompt-format)
- [PromptKit Prompt Attributes](#prompt-attributes)
- [Handling Responses](#handling-responses)
- [PromptKit Stories](#promptkit-stories)


<span id="prompt-format"></span>
### PromptKit Prompt Dictionary Format
At the heart of every prompt is a dictionary that specifies what kind of prompt PromptKit will display. The Prompt dictionary can be provided to PromptKit in three ways: Dictionary, JSON, or text. The screenshot below shows the exact same Prompt written in these three formats:

![PromptKit Prompt Format](https://adamtow.github.io/promptkit/images/prompt-format.png)

#### Dictionary

Shortcut's visual interface makes adding, editing, and removing elements from a dictionary object easy.

![Dictionary Text Format](https://adamtow.github.io/promptkit/images/format-text-dictionary.png)

> NOTE: As your PromptKit Prompt and Story dictionaries get large, you may encounter some odd bugs with the Shortcut app (disappearing fields or fields that you can edit). At this point, you may want to consider supplying your PromptKit dictionaries in JSON. 

#### JSON

If you are making PromptKit Prompts and PromptKit Stories from a desktop or laptop computer, you may be more comfortable creating your story in an editor tailored for creating JSON files.

![JSON Text Format](https://adamtow.github.io/promptkit/images/format-text-json.png)

```
{
	"type": "text",
	"mode": "handsfree",
	"message": "How are you doing?"
}
```

> NOTE: If you use JSON, be sure to have a Get Dictionary From Input action before the call to Run Shortcut. Also be sure that your quotes are not getting converted to smart quotes. 

#### Text

If you just supply a text string, it will be interpreted as a freeform text prompt:

![Plain Text Format](https://adamtow.github.io/promptkit/images/format-text-plain.png)

```
How are you doing?
```

You can replicate a PromptKit Dictionary with plaintext by separating key/value pairs with the 🔑 and 🗝 emoji characters. The format is:

`🔑 KEY 🗝 VALUE 🔑`

![Text Format](https://adamtow.github.io/promptkit/images/format-text.png)

```
🔑 type 🗝 text 🔑

🔑 mode 🗝 manual 🔑

🔑 message 🗝 How are you doing?🔑
```

<span id="prompt-attributes"></span>
### PromptKit Prompt Attributes

A PromptKit Prompt and Scene are dictionaries that contain the following attributes. You can create these within the Shortcuts app or in a text editor. 

- [message](#message)
- [key](#key)
- [type](#type)
- [mode](#mode)
- [title](#title)
- [choices](#choices)
- [spokenLanguage](#spokenLanguage)
- [dictationLanguage](#dictationLanguage)
- [repeat](#repeat)
- [validate](#validate)

**Additional Options**

- [speakChoices](#speakChoices)
- [notificationPlaySound](#notificationPlaySound)
- [confirmShowCancel](#confirmShowCancel)
- [allowEmptyResponse](#allowEmptyResponse)
- [allowTranslations](#allowTranslations)
- [allowTranslationDictation](#allowTranslationDictation)
- [returnResponseOnly](#returnResponseOnly)

**Story-Specific Attributes and Options**

- [dataKey](#dataKey)
- [decisions](#decisions)
- [hideFromHistory](#hideFromHistory)

****

### message - Text or Array
This is the information displayed or spoken to the user. If you supply just one string, it will be used for all repetitions. If you supply multiple strings in an array, the string used will correspond to the loop repeat index. For instance:

```
"message":
	[
		"Pick a number between 1 and 5.",
		"Any number between 1 and 5.",
		"It's not that hard, choose a number between 1 and 5.",
		"1. 2. 3. 4. or 5. Come on now."
	]
```

The first time PromptKit is called, it will speak the first question string. If a successful response is not given, it will speak the second question, followed by the third and fourth. If the user did not provide a successful response after the fourth, the function will return with a ❓ response.

****

## type (Optional) Text
Specifies how the message will be interpreted and presented to the user. Valid values include:

- **alert**: Displays the message in a modal alert dialog for manual prompts. If specified, the `title` of the prompt will be used as the title of the alert. Otherwise "PromptKit" will be used. Tapping OK will continue the execution of PromptKit. Tapping Cancel will terminate the shortcut. For handsfree prompts, the message is spoken to the user. 
- **confirm**: Prompts the user for a Yes, No, or optional Cancel response.
- **date**: Prompts the user to enter a date. Manual prompts will display the standard iOS Date picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date. 
- **dateTime**: Prompts the user to enter a date and time. Manual prompts will display the standard iOS Date and Time picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date and time. 
- **list**: Prompts the user to choose from a list of choices.
- **history**: in PromptKit Stories, this Prompt type allows the user to go back to a previous point in a Story. For both manual and handsfree prompts, it displays a menu of available scenes to return to. More information on how history works can be found in the [PromptKit Story History](#promptkit-story-history) section. 
- **html**: Interprets the message as HTML, converts it to a webpage and displays in a Quick Look window or Safari window. Specify `useSafari` to true to open the URL in Safari. 
- **none**: No message is displayed to the user. This type is used commonly in PromptKit Stories as a separator between scenes. 
- **notification**: Displays the message in a notification banner with manual driven prompts. If specified, the `title` of the prompt will be used as the title of the notification. Otherwise "PromptKit" will be used. Specify `notificationSound` to true to display a sound during the notification (default is no sound). For handsfree prompts, the message is spoken to the user. 
- **number**: Prompts the user to enter a number. Verifies that the user entered a valid number. Supports validation tests of equality, less than, greater than, and between. 
- **quickLook**: Displays the message in a Quick Look window for manual prompts. For handsfree prompts, the message is spoken back to the user. 
- **result**: Displays the message in a modal dialog for manual prompts. For handsfree prompts, the message is spoken to the user. 
- **speak**: Speaks the message to the user.
- **text** (default): For manual prompts, the message is displayed in an Ask For Input action dialog. For handsfree prompts, the message is spoken to the user and Dictate Text action captures the user's input. This type can be combined with the `choices` array to accept only certain responses.
- **time**: Prompts the user to enter a time. Manual prompts will display the standard iOS Time picker. Voice prompts will use the Get Dates From Input and Format Dates actions to convert dictated text into a time. 
- **url**: Opens a Quick Look window or Safari to the supplies URL. Specify `useSafari` to true to open the URL in Safari. 

Voice-driven prompts can specify the `speakChoices` option to verbally list out the choices after speaking the message. 

****

## choices (Optional) Array of strings
If specified, the response will be compared with the values in the `choices` array. Each value in the array can have optional matching strings, delimited by the `|` character. For instance:

```
{
	"message": "What mapping application would you like to use?",
	"choices":
		[
			"Maps | Apple Maps | Apple",
			"Google Maps | Google",
			"Waze"
		]
}
```

When run, the user will be prompted to choose a default maps app. The user could say "Maps", "Apple Maps", or "Apple" in order to select the "Maps" choice. For "Google Maps", the only two choices are "Google Maps" and "Google". "Waze" is the only choice for the final answer.

You can use the | delimiter with both Freeform and Number prompts. Confirm prompts make use of the Localized Strings dictionary to determine yes or no responses.

****

### validate (Optional) String
By default, your response will be matched to possible answers in the `choices` array using a contains comparison. You can specify the following values for `validate`:

- **contains** (default for text)
- **equals** (default for numbers)
- **exact**
- **greaterThan** (numbers only)
- **lessThan** (numbers only)
- **between** (dates, times, and numbers only)
- **before** (dates and times only)
- **after** (dates and times only)

#### contains
If you said, "I really like brownies." and the `choices` has the following:

```
{
	"message": "What is your favorite dessert?",
	"type": "handsfree",
	"choices":
		[
			"cake",
			"ice cream | sorbet | gelato",
			"brownie | brownies",
			"pie | cobbler"
		]
}
```

PromptKit will look if your input contains any words in any of the choices. In this case, the third choice would match your input and the response returned would be "brownie".

On the other hand, if you entered, "While I enjoy a good piece of cake, I really prefer brownies," PromptKit will choose and return cake since it was the first keyword match. PromptKit does not perform any complicated analysis of your input. If you desire this, consider [sending the input to a shortcut](#shortcuts). 

#### equals
Using the example above, "I really like brownies," would not match any of the choices. You would have to say, "brownies" or "brownie" in order to match the brownies choice. Input is lowercase for string comparison purposes. 

#### exact
The original input (trimmed of any whitespace from the beginning and end) is compared in a case-sensitive exactly with the strings in the `choices` array. 

It is not recommended to use exact comparison with prompts of the type handsfree since you have less control over the casing of your input. 

#### greaterThan
For use with numbers, the input must be greater than any of the numbers in items within the `choices` array. 

#### lessThan
For use with numbers, the input must be less than any of the numbers in items within the `choices` array. 

#### between
For use with numbers and dates, the input must be between any of the numbers in items within the `choices` array. Use an en dash `–` character as a delimiter between the lower and upper bounds. For instance:

`"choices": "1–10 | 20–30"`

****

<span id="repeat"></span> 
### repeat
(Optional) Number
You can specify how many times PromptKit will ask the user your question. The default is 5. If at the end of the repeat loop, the user still has not answered the question, the ❓ string will be returned in the [**Response Dictionary**](#response-dictionary).

****

<span id="spokenLanguage"></span> 
### spokenLanguage 
(Optional) Text
Setting the language will determine the language used to speak the prompt's message. It also controls how the Yes, No, and Cancel choices in Confirm prompts are displayed.

The format of the dictation language is (language code)-(country code). For instance:

- **en-US**: English (USA)
- **en-GB**: English (United Kingdom)
- **fr-FR**: French (France)

****

<span id="dictationLanguage"></span> 
### dictationLanguage 
(Optional) Text
Setting the dictationLanguage will determine how Dictate Text Action interprets user input. If not specified, the dictation language will be the same as the spoken language. 

The format of the dictation language differs from the of spokenLanguage in that you can also specify just the two letter language code. Region is optional:

- **en**: English
- **en-US**: English (USA)
- **en-GB**: English (United Kingdom)
- **fr**: French
- **fr-FR**: French (France)

A complete list of [supported languages and codes](#language-codes) can be found here. 

****

### Additional Boolean Options

The following attributes are boolean values that provide additional options for Prompts.

<span id="alertShowCancel"></span>
#### alertShowCancel (default: false)

For alert prompts, this will add the Cancel button to the alert. 

NOTE: Tapping Cancel will terminate shortcut execution. 

<span id="allowEmptyResponse"></span>
#### allowEmptyResponse (default: false)
If true, an empty response can be returned back to the calling shortcut. Otherwise, PromptKit will repeat the prompt until a response is provided or the repeat count is reached.

The default value for `allowEmptyResponse` is false.

<span id="allowTranslations"></span>
#### allowTranslations (default: true)

By default, this option is set to true for all Prompts. Setting it to false will prevent a message from being translated. Use this if you want your prompt to be spoken in the specified language, rather than the translated language.

<span id="allowTranslationDictation"></span>
#### allowTranslationDictation (default: true)

When Auto Translate is on, it may be difficult to translate the list of possible choices into the translation language. Some words may not translate very well, for instance. By default, PromptKit will switch to `manual` mode and raise dialogs and menus when Auto Translate is active. 

Setting `allowTranslationDictation` to true allows your handsfree prompt to continue in handsfree mode. Possible responses will be translated and be available, along with the original responses. For instance:

- Driving | Car | Drive | Auto

Will gain additional matching responses in French:

- La conduite | Voiture | Disque dur | auto

As you can see, the translation performed by Microsoft Cognitive Services sometimes makes mistakes. 

> Every alternate word you provide may be translated, which can lead to slowdowns if you have a lot of alternate words in the `choices` array. Balance the ability for the user to say alternate phrases with performance when Auto Translate is enabled. 

Remember that you can specify multiple modes in the mode attribute by separating the modes with a | character. If you set your mode to handsfree, you may want to consider supplying a manual mode at the end:

`"mode": "handsfree | handsfree | manual"`

For the first two attempts, handsfree mode will be used. Afterwards, manual mode will be employed. 

<span id="confirmShowCancel"></span>
#### confirmShowCancel (default: false)

For confirm prompts, this adds a PromptKit Cancel 🛑 option. Choosing this allows developers to handle cases other than Yes or No. 

<span id="hideFromHistory"></span> 
#### hideFromHistory  (default: false)

For use with PromptKit Scenes and Stories, this will prevent a Scene from being added to the history list. 

<span id="notificationPlaySound"></span>
#### notificationPlaySound (default: false)

For notification prompts, setting this value to true will play a sound when the notification banner appears. 

<span id="returnResponseOnly"></span>
#### returnResponseOnly (default: true)

By default, PromptKit returns the response chosen by the system. Setting this flag to false will return the entire PromptKit Response Dictionary. 

<span id="speakChoices"></span> 
#### speakChoices (default: false)

If a prompt type has a list of possible choices, setting this value to true in the Prompt Dictionary will cause PromptKit to list out the choices audibly in `handsfree` mode. 

****

<span id="handling-responses"></span>
## Handling Responses
When PromptKit has finished processing your prompt it will return either a string representing the prompt's response or a PromptKit Response dictionary object.

![PromptKit Response Only](https://adamtow.github.io/promptkit/images/response-only.png)

By default, a string response will be returned. In the screenshot below, a confirm prompt is displayed and the returned value is 1 because Yes was tapped.

****

### Response Dictionary
If `returnResponseOnly` is false, PromptKit will return a PromptKit Response Dictionary. This dictionary contains more information about the PromptKit interaction the user had with your shortcut. It includes the following components:

![PromptKit Response Dictionary](https://adamtow.github.io/promptkit/images/response-dictionary.png)

- **response**: The accepted response from the user or one of control emoji symbols, such as 🛑 or ❓.
- **responses**: Each response from the user is recorded in this array.
- **original**: What the user said (as interpreted by iOS) to produce the Response value.
- **lowercase**: A lowercased version of the response. 
- **cleaned**: the response stripped of whitespace from the beginning and end of the response. 
- **repeatIndex**: The index from the repeat loop when PromptKit exited.

#### Understanding the Emoji and Confirmation Responses
If the response contains the following emoji symbols, you should interpret them as follows:

- 🛑: The user spoke a cancel phrase.
- ❓: The user did not speak anything that led to a successful response. This is sent when the `repeat` count has been reached in a prompt. 

Prompts of the `confirm` type will return either 1, 0, or 🛑.

- 1: The user spoke one of the YES phrases. Used with the `Confirm` prompts.
- 0: The user spoke one of the NO phrases. Used with the `Confirm`  prompts.
- 🛑: The user tapped the special 🛑 menu item. This can be enabled by specifying true to the `confirmShowCancel` Prompt attribute.

> Pressing the large Cancel button in Alert, Choose From Menu, and Choose From List menus terminates shortcuts, so the 🛑 is added as a way to provide a user cancel option without cancelling the shortcut.

For completeness, your shortcut should handle each of these cases. 

****

### PromptKit Stories

<span id="promptkit-story"></span>
#### PromptKit Story
A PromptKit Story is collection of PromptKit Prompts forms the basis of a PromptKit Story. A story can be build to create simple or complex interactive voice or menu-driven experiences on iOS. PromptKit dictionaries that belong to a story have additional attributes. 

A PromptKit Story dictionary must contain the following fields:

- [**promptKitStory**](#promptKitStory): Boolean set to true.
- [**start**](#start): Text set to the first scene to run.
- [**scenes**](#scenes): An array of PromptKit Prompts that will be the scenes of the Story.

Optional fields include:

- [**data**](#data): A dictionary containing the starting data object for the Story.
- [**mode**](#mode): The default mode to use for scenes that do not have a mode specified.

#### PromptKit Scenes

A PromptKit Scene is just a PromptKit Prompt dictionary with some additional attributes.

![PromptKit Story Dictionary Formats](https://adamtow.github.io/promptkit/images/story-dictionaries.png)

<span id="dataKey"></span>
##### dataKey

The matching choice in the `choices` array will be placed into the `dataKey` value inside the `data` dictionary.

> Note you can use the PromptKit Decision string to specify additional key/value pairs of data to store into the `data` dictionary.

<span id="decisions"></span>
##### decisions

This is a text string or an array of [PromptKit Decision](#handling-decisions) text strings that determine what happens when a successful choice is chosen. The format of a PromptKit Decision can follow one of two formats. Parameters are separated by the `|` character.

<span id="hideFromHistory"></span>
#### hideFromHistory

Hide this scene from the [PromptKit History object](#promptkit-story-history). 

<span id="handling-decisions"></span>
### Handling Decisions

Responding to choices and input by the user is the backbone to running a successful PromptKit Story.

#### Decision Key

In both formats, the first parameter is always the Decision Key, which is the **exact** value from the first item in `choices` array. If `choices` is a text string, the Decision Key must match that string.

##### Run Shortcut

`Decision Key | ▶ Shortcut Name | Scene Name | dataKey1 | dataValue1 | dataKey2 | dataValue2`

If you want to run a shortcut, the second parameter must contain the ▶ character followed by the exact name of the shortcut you want to run.

Shortcuts are sent a dictionary containing scene and data information, along with the `promptKitStory` parameter set to true.

> Note: PromptKit will terminate if the shortcut could not be found.

##### Scene

`Decision Key | Scene Name | dataKey1 | dataValue1 | dataKey2 | dataValue2`

If you want to go to another scene, the second parameter is the scene name.

##### Decision Parameters

Following the scene name is an optional series of key/value pairs. The dataKey is the key used to store the dataValue in the `data` dictionary of the Story.

<span id="promptkit-history"></span>
#### PromptKit Story History

PromptKit keeps track of where the user is while going through a Story, and provides the ability to go back to any previous point in the Story.

You can use the `history` Prompt type to display a history menu. The Story date will be restored to the exact point in the history. Data that was captured after the restore point will be lost.

<span id="calling-shortcuts"></span>
### Calling External Shortcut Shortcuts
To call a shortcut from a Scene, you specify the name of the shortcut in a Decision String:

`eggs | ▶️ Egg Maker | eat | eggMade | {{shortcut}}`

If the user chose eggs from the previous step, the shortcut named “Egg Maker” will be launched. The result of the shortcut will be placed as the value to the `eggMade` key in the Scene’s `data` dictionary. Finally, PromptKit will look for an execute the `eat` scene in the Story. 

Shortcuts called from a PromptKit Story are supplied a dictionary with the following fields:

- **promptKitStory**: Boolean value that is 1.
- **scene**: the name of the scene being run. 
- **data**: the current data containing state information and variables from the Story. 

### Modifying and Return the Data Object
Normally a shortcut’s return value will be used to populate a single key with a Scene. However, you can also return the entire `data` dictionary back to PromptKit. This data object will replace the current object and will be used for subsequent prompts. 

This is useful if you are calculating or processing information stored within a Story or Scene. Suppose you are creating an expert system that makes a recommendation based on the decisions a user has chosen. After collecting all of the data, PromptKit can dispatch the data object to the shortcut that performs all the weighing, calculating, and interpreting. The shortcut would then replace the entire data object with the new one created in the shortcut. 

To copy and replace the existing Story.data object with a new one, structure the Decision String as follows:

`key | My Shortcut | nextScene | * | {{Shortcut}}`

The * character here tells PromptKit to save the data object back to the Story. 

### Terminating PromptKit From A Shortcut
If your external shortcut returns ⏹⏹⏹ to PromptKit, execution will stop the current story and PromptKit will exit.

### Using PromptKit with Cronios
If you use PromptKit with [Cronios, the shortcuts scheduler for iOS](http://cronios.com), you'll want to be aware of how the shortcut operates when in the background.

In order to present alerts, prompts, and the dictation screen to the user, Shortcuts must be the frontmost application. When run, PromptKit will switch to the Shortcuts app automatically. 

#### Lock Detection
If you have enabled [Lock Detection](#lock-detection), PromptKit will audibly prompt the user to unlock his or her device prior to displaying the prompt. If disabled, PromptKit will silently exit and the prompt will not be presented.

<span id="best-practices"></span>
### Best Practices
- Make use of the `speakChoices` option to have PromptKit speak what choices are available in Speech with Dictation mode. 
- Switch to manual mode on the the last attempt at getting user input. In the `mode` parameter, you can specify multiple modes with pipes. For instance: `handsfree | handsfree | mode` will cause dictation to be used for the first two attempts. On the third and final attempt, PromptKit will display a dialog. 
- Provide alternate responses for each choice. Adding more terms for choices gives the translation engine more of a chance to find a word it can translate. For instance, if you are asking the user for driving, walking, or transit directions, you can specify your choices as:
	- `Driving | Drive | Auto | Car | Automobile`
	- `Walking | Walk | By Foot | Hike | Hiking | Bike | Cycle | Biking`
	- `Transit | Public | Transportation | Bus | Subway | Metro | Train`

****

<span id="languages"></span>
## Languages
PromptKit natively supports translating between the following languages:

- Arabic
- Cantonese (Traditional)
- Chinese Traditional
- Chinese Simplified
- Czech
- Danish
- Dutch
- English
- Finnish
- French
- German
- Greek
- Hebrew
- Hindi
- Hungarian
- Indonesian
- Italian
- Japanese
- Korean
- Norwegian
- Polish
- Portuguese
- Romanian
- Russian
- Slovak
- Spanish
- Swedish
- Thai
- Turkish

The strings here match exactly with those presented by the **Translate Text with Microsoft** action.

![Languages: Translate, Dictate, and Speak](https://adamtow.github.io/promptkit/images/languages.png)


<span id="language-codes"></span>
### Language Codes

The following language codes are supported for `spokenLanguage` and `dictationLanguage` attributes respectively within a PromptKit Prompt or Story dictionary.

> You'll note that there are more dictation languages than are supported by PromptKit. This is because there is no corresponding spoken language support for the dictation language. When Apple adds support for these, PromptKit will support them too!

For language code in the format of `xx-YY` where `xx` is the [ISO-649-1](https://en.m.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code and `YY` is the [ISO-3166](https://en.m.wikipedia.org/wiki/ISO_3166-1) 2-letter country code. 

#### Spoken Languages

- **ar-SA**: Arabic (Saudi Arabia)
- **zh-CN**: Chinese (China)
- **zh-HK**: Chinese (Hong Kong [China])
- **zh-TW**: Chinese (Taiwan)
- **cs-CZ**: Czech (Czechia)
- **da-DK**: Danish (Denmark)
- **nl-BE**: Dutch (Belgium)
- **nl-NL**: Dutch (Netherlands)
- **en-AU**: English (Australia)
- **en-AU**: English (Australia)
- **en-IE**: English (Ireland)
- **en-ZA**: English (South Africa)
- **en-GB**: English (United Kingdom)
- **en-US**: English (United States)
- **fi-FI**: Finnish (Finland)
- **fr-CA**: French (Canada)
- **fr-FR**: French (France)
- **de-DE**: German (Germany)
- **el-GR**: Greek (Greece)
- **he-IL**: Hebrew (Israel)
- **hi-IN**: Hindi (India)
- **hu-HU**: Hungarian (Hungary)
- **id-ID**: Indonesian (Indonesia)
- **it-IT**: Italian (Italy)
- **ja-JP**: Japanese (Japan)
- **ko-KR**: Korean (South Korea)
- **nb-NO**: Norwegian (Norway)
- **pl-PL**: Polish (Poland)
- **pt-BR**: Portuguese (Brazil)
- **pt-PT**: Portuguese (Portugal) 
- **ro-RO**: Romanian (Romania)
- **ru-RU**: Russian (Russia)
- **sk-SK**: Slovak (Slovakia)
- **es-MX**: Spanish (Mexico)
- **sv-SE**: Swedish (Sweden)
- **th-TH**: Thai (Thailand)
- **tr-TR**: Turkish (Turkey)

#### Dictation Languages:

- **ar**: Arabic
- **ar-SA**: Arabic (Saudi Arabia)
- **zh**: Chinese
- **zh-Hant-HK**: Cantonese (China Mainland)
- **ca**: Catalan
- **ca-ES**: Catalan (Spain)
- **zh-CN**: Chinese (China Mainland)
- **zh-HK**: Chinese (Hong Kong)
- **zh-TW**: Chinese (Taiwan)
- **hr**: Croatian
- **hr-HR**: Croatian (Croatian)
- **cs**: Czech
- **cs-CZ**: Czech (Czechia)
- **da**: Danish
- **da-DK**: Danish (Denmark)
- **nl**: Dutch
- **nl-BE**: Dutch (Belgium)
- **nl-NL**: Dutch (Netherlands)
- **en**: English
- **en-AU**: English (Australia)
- **en-CA**: English (Canada)
- **en-IN**: English (India)
- **en-ID**: English (Indonesia)
- **en-IE**: English (Ireland)
- **en-NZ**: English (New Zealand)
- **en-PH**: English (Philippines)
- **en-SA**: English (Saudi Arabia)
- **en-SG**: English (Singapore)
- **en-ZA**: English (South Africa)
- **en-AE**: English (United Arab Emirates)
- **en-GB**: English (United Kingdom)
- **en-US**: English (United States)
- **fi**: Finnish
- **fi-FI**: Finnish (Finland)
- **fr**: French
- **fr-BE**: French (Belgium)
- **fr-CA**: French (Canada)
- **fr-FR**: French (France)
- **fr-CH**: French (Switzerland)
- **de**: German
- **de-AT**: German (Austria)
- **de-DE**: German (Germany)
- **de-CH**: German (Switzerland)
- **el**: Greek
- **el-GR**: Greek (Greece)
- **he**: Hebrew
- **he-IL**: Hebrew (Israel)
- **hi**: Hindi
- **hi-IN**: Hindi (India)
- **hu**: Hungarian
- **hu-HU**: Hungarian (Hungary)
- **id**: Indonesian
- **id-ID**: Indonesian (Indonesia)
- **it**: Italian
- **it-IT**: Italian (Italy)
- **it-CH**: Italian (Switzerland)
- **ja**: Japanese
- **ja-JP**: Japanese (Japan)
- **ko**: Korean
- **ko-KR**: Korean (South Korea)
- **ms**: Malay
- **ms-MY**: Malay (Malaysia)
- **nb**: Norwegian
- **nb-NO**: Norwegian Bokmål (Norway)
- **pl**: Polish
- **pl-PL**: Polish (Poland)
- **pt**: Portuguese
- **pt-BR**: Portuguese (Brazil)
- **pt-PT**: Portuguese (Portugal)
- **ro**: Romanian
- **ro-RO**: Romanian (Romania)
- **ru**: Russia
- **ru-RU**: Russia (Russian)
- **sk**: Slovak
- **sk-SK**: Slovak (Slovakia)
- **es**: Spanish
- **es-CL**: Spanish (Chile)
- **es-CO**: Spanish (Colombia)
- **es-MX**: Spanish (Mexico)
- **es-ES**: Spanish (Spain)
- **es-US**: Spanish (United States)
- **sv**: Swedish
- **sv-SE**: Swedish (Sweden)
- **th**: Thai
- **th-TH**: Thai (Thailand)
- **tr**: Turkish
- **tr-TR**: Turkish (Turkey)
- **uk**: Ukrainian
- **uk-UA**: Ukrainian (Ukraine)
- **vi**: Vietnamese
- **vi-VN**: Vietnamese Vietnam)

<span id="language-dictionary"></span>
### Language Dictionaries
Powering each translatable language is a PromptKit Language Dictionary. It contains common terms and phrases used by PromptKit to handle:

- Converting written numbers to their numeric equivalent.
- Phrases for speaking list choices to provide variation. 
- Spelling of localized language string in the Translate Text to Microsoft action. 
- Language codes and regions. 

Improve the performance and accuracy of PromptKit by contributing to a language dictionary. 

You can find the current set of [language dictionaries on GitHub here](https://github.com/adamtow/promptkit/blob/master/localization/language-dictionaries/).

Each language dictionary is a dictionary object whose primary key within the root dictionaries object is the language code or language + country.

```
{
	"en": { … },
	"en-UK": { … },
	"en-US": { … },
}

Three language dictionaries handle generic English, British English, and American English. 

```

Each language dictionary has the following required properties:

- **name**: name of the language. 
- **code**: two-letter language code. 
- **languageCode**: language code + region string.
- **countries**: an array of supported regions for the language dictionary.
- **phrases**: a dictionary containing:
	- **bigNumbers**: a dictionary mapping for numbers that are converted to words by dictation (i.e. million, billion, and trillion). See English language dictionary as an example.
	- **cancel**: an array of strings that are keyword phrases for the cancelling out of prompts. The first string is also displayed as an option in a confirmation prompt. 
	- **no**: an array of strings for saying NO in a confirmation prompt. 
	- **numbers**: written out words that need to be changed to numbers when dictating text. If you try to say the number 1, Siri will often return the text, "One". Listing out the names of the numbers here (in order from zero) will allow PromptKit to convert the text into a number. 
	- **or**: a single line of text that says "or" in the given language. 
	- **say**: a string or array of strings that are phrases to say when PromptKit is listing out choices a user can say to successfully complete a prompt. These choices are spoken when the `speakChoices` Prompt attribute is true. See the English language dictionary for examples. 
	- **unlockPrompt**: The localized version of the string used with the [Lock Detection feature](#lock-detection) of PromptKit. 
	- **yes**: an array of strings for saying YES in a confirmation prompt. 
- **supportedLanguages**: The localized name of supported languages as displayed by the Translate Text with Microsoft action in Shortcuts. 

Here is an example of the English language dictionary object:

```
"en": {
		"name": "English",
		"code": "en",
		"languageCode": "en-US",
		"countries": [
			"US",
			"GB",
			"CA"
		],
		"phrases": {
			"bigNumbers": {
				"million": "1000000",
				"billion": "1000000000",
				"trillion": "1000000000000"
			},
			"cancel": [
				"🛑",
				"Cancel"
			],
			"no": [
				"No",
				"Never",
				"Negative"
			],
			"numbers": [
				"zero",
				"one",
				"two",
				"three",
				"four",
				"five",
				"six",
				"seven",
				"eight",
				"nine",
				"ten"
			],
			"or": "Or",
			"say": [
				"Say:",
				"Choose from:",
				"Pick from:",
				"You can say:"
			],
			"unlockPrompt": "PromptKit is requesting your attention. Please unlock your device to respond to the prompt.",
			"yes": [
				"Yes",
				"Okay",
				"Yeah",
				"Ok",
				"Affirmative"
			]
		},
		"supportedLanguages": [
			"Arabic",
			"Cantonese (Traditional)",
			"Chinese Simplified",
			"Chinese Traditional",
			"Czech",
			"Danish",
			"Dutch",
			"English",
			"Finnish",
			"French",
			"German",
			"Greek",
			"Hebrew",
			"Hindi",
			"Hungarian",
			"Indonesian",
			"Italian",
			"Japanese",
			"Korean",
			"Norwegian",
			"Polish",
			"Portuguese",
			"Romanian",
			"Russian",
			"Slovak",
			"Spanish",
			"Swedish",
			"Thai",
			"Turkish"
		]
	}
```

****

<span id="localization"></span> 
## Localization
PromptKit is available in English, but the application is also supplied with auto-translated localized files for the support spoken/dictation languages.

Since machine translation is never perfect, your help would come greatly in handy. If you are a native speaker of one of these languages, consider contributing to improving PromptKit's localization files.

You can use the Localization Helper shortcut to assist with localizing PromptKit into your language.

> [**Download Localization Helper from RoutineHub &raquo;**](https://routinehub.co/shortcut/1931)

- When the localization file is complete, submit a pull request on [the PromptKit GitHub page](https://github.com/adamtow/promptkit/tree/master/localization/application).

You can also inspect the files for each supported language's language dictionary in the `localization/application` directory. This contains information such as alternate phrases for Yes, No, and Cancel, numbers, localized version of support translation languages (for the Translate Text with Microsoft action), and more. Help make PromptKit more accurate and more universal for all iOS users!

****

<span id="app-framework"></span>
## App Framework
PromptKit was developed using the [Shortcut App Framework](https://routinehub.co/shortcut/1510) approach to developing application-like shortcuts. This framework was also used to develop:

- [**Cronios**](https://routinehub.co/shortcut/1267): The shortcuts scheduler for iOS.
- [**GeoCuts**](https://routinehub.co/shortcut/1732): Run your shortcuts automatically based on location triggers.
- [**Inspector**](https://routinehub.co/shortcut/1106): View and modify objects at runtime in your shortcuts.
- [**LaunchCuts**](https://routinehub.co/shortcut/959): Folders and tags for your organizing and launching your shortcuts.
- [**WatchCuts**](https://routinehub.co/shortcut/1864): Trigger shortcuts on your iPhone and iPad using any of your iCloud-connected devices: iPhone, iPad, Mac, Apple Watch, or iCloud.com!

Learn more how you can create your own [shortcut applications with App Framework here](https://tow.com/shortcuts/framework).

****

<span id="troubleshooting"></span> 
## Troubleshooting
Have a problem with PromptKit?

- **Why are prompts slow to generate?** Do you have Detect Languages and Auto Translate enabled? Both features require an active connection to the internet, and both employ Microsoft Cognitive Services to provide language detection and translation services. Should there be any network slowdowns, it will impact the performance of PromptKit.
- **Why are all my prompts using dialogs or speech?** Did you turn on Mode Override? That feature switches the mode of all prompts to use either dialogs, speech with dialogs, or speech with dictation. Turn off Mode Override so the prompts can determine what mode they run in. 

****

<span id="license"></span>
## License

>Copyright (c) 2019 Adam Tow • tow.com • @atow
>
>Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
>
>The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
>
>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
