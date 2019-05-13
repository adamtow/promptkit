# PromptKit
PromptKit is a shortcut library for creating powerful, interactive, multilingual prompts featuring speech, dictation, menus, and dialogs. PromptKit makes interacting with your iOS device even better. 

## Quick Links
- [**Download PromptKit From RoutineHub**](https://routinehub.co/shortcut/2583)
- [Get PromptKit Tester](https://routinehub.co/shortcut/2628), a shortcut that showcases the ways PromptKit can present and request information.
- [Find more shortcuts that support PromptKit](https://routinehub.co/search/?q=PromptKit)

## Table of Contents
- [Overview](#overview)
- [Download](#download)
- [Getting Started](#getting-started)
- [Using PromptKit](#using-promptkit)
- [Exploring PromptKits Interface](#interface)
- [Settings](#settings)
- [Developer for PromptKit](#developer)
- [Localization](#localization)
- [App Framework](#app-framework)
- [Troubleshooting](#troubleshooting)
- [License](#license)

<span id="overview"></span> 
## PromptKit Overview
PromptKit serves both end-users and developers alike. For users, PromptKit give them the ability to:

- Have richer and more interactive experiences with their iOS devices. 
- Select between voice or dialog-driven prompts.
	- Not connected to the internet? Voice-driven prompts will turn into menu and dialog prompts.
- Automatically translate prompts from one language to another. 
	- Over 25 languages supported out of the box. 
- Configure PromptKit to work exclusively in handsfree mode or dialog-driven mode. 

Developers benefit from an easy-to-use API that gives them the ability to:

- Choose from an extensive list of prompt types, including:
	- Freeform
	- Numbers
	- Dates and times
	- Yes and no confirmations
	- Alerts and notifications
- Restrict prompts to accept a list of answers. Each answer can have multiple alternate responses.
- Validate user input with comparison operators such as:
	- contains
	- equals
	- exact equality
	- greater than
	- less than
	- between
	- before
	- after
	- between
- Repeat the prompt once or multiple times if the input is not validated. Optionally change the prompt message or type on each repetition of the prompt. 
- Detect cancellation, no response, and successful responses by the user.

### PromptKit Stories
PromptKit Prompts can be bundled together as scenes of a PromptKit Story. Stories extends the power of PromptKit by creating rich, multi-step interactions with your iOS device.

For developers, making a prompt with PromptKit is as easy as sending it some text or a dictionary of options. Learn more about its API to unlock its full potential, including the ability to:

- Send and receive data from external shortcuts. 
- Store and share data between story scenes. 
- Access a history of past prompts (i.e. go back to step 4 or start over from the beginning). 

<span id="getting-started"></span>
## Getting Started
Get started by downloading and installing PromptKit. The latest version is available on RoutineHub:

<span id="download"></span> 
- [**Download PromptKit**](https://routinehub.co/shortcut/2583)

After installing, run PromptKit from the Shortcuts Home screen. It’s a large shortcut with over 3500 actions, so it will take a long time to run from the Edit Shortcut Screen. 

### Setup Assistant
The first time you run PromptKit, the setup assistant will walk you through the steps of configuring the shortcut. Each of the menus and prompts you see were
created using PromptKit’s easy to build API. You will learn about:

- **Check for Updates**: Configure PromptKit to check for updates automatically at startup of the main application. It will not happen while running prompts. 
- **Detect Languages**: Determine the language of a prompt so PromptKit can provide these benefits to you. 
	- **Auto Translate**: Set PromptKit to translate prompts from one language to another. Choose from over 25 supported languages. 
	- **Translation Dictation**: For prompts that employ dictation, this setting allows you to provide your response in the dictated languages. If a prompt was originally set to English and you are translating to French, you can respond back in French. 
- **Default Mode**: for prompts that don’t specify a mode of operation (i.e. dialog or voice driven prompts), PromptKit will use the setting you choose  here. 
- **Mode Override**: PromptKit allows the user to override all modes and use just one way to interact with PromptKit Prompts. 
- **Ask Story Mode**: When starting a PromptKit Story, PromptKit can force a story to run temporarily in one mode. 

Once setup is complete, you can [find more PromptKit compatible shortcuts](https://routinehub.co/search/?q=PKS) on RoutineHub, read the documentation, or go to the PromptKit Home screen. 

<span id="using-promptkit"></span>
## Using PromptKit

<span id="interface"></span>
## Exploring PromptKits Interface

<span id="settings"></span>
## PromptKit Settings

<span id="developer"></span>
## Developer API

## PromptKit Dictionary
PromptKit supports text and dictionary input. Specifying the PromptKit Dictionary gives you the most control over the look and feel of your prompt.

## PromptKit Stories
A PromptKit Story is collection of PromptKit Prompts forms the basis of a PromptKit Story. A story can be build to create simple or complex interactive voice or menu-driven experiences on iOS. PromptKit dictionaries that belong to a story have additional attributes. 

### Exploring a PromptKit Prompt
A PromptKit Prompt and Scene are dictionaries that contain the following required and option attributes. You can create these within the Shortcuts app or in a text editor. 

**Required**
- [message](#message)

**Optional**
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
- [speakChoices](#decisions)
- [hideFromHistory](#hideFromHistory)
- [notificationPlaySound](#notificationPlaySound)
- [confirmShowCancel](#confirmShowCancel)
- [allowTranslationDictation](#allowTranslationDictation)
- [returnResponseOnly](#returnResponseOnly)

**Story-Specific Options**
- [decisions](#decisions)
- [dataKey](#dataKey)

### message (Required) Text or Array
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

## type (Optional) Text
Specifies how the message will be interpreted and presented to the user. Valid values include:

- **text** (default): For manual prompts, the message is displayed in an Ask For Input action dialog. For handsfree prompts, the message is spoken to the user and Dictate Text action captures the user’s input. This type can be combined with the `choices` array to accept only certain responses.
- **confirm**: Prompts the user for a Yes, No, or optional Cancel response.
- **number**: Prompts the user to enter a number. Verifies that the user entered a valid number. Supports validation tests of equality, less than, greater than, and between. 
- **list**: Prompts the user to choose from a list of choices.
- **date**: Prompts the user to enter a date. Manual prompts will display the standard iOS Date picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date. 
- **dateTime**: Prompts the user to enter a date and time. Manual prompts will display the standard iOS Date and Time picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date and time. 
- **time**: Prompts the user to enter a time. Manual prompts will display the standard iOS Time picker. Voice prompts will use the Get Dates From Input and Format Dates actions to convert dictated text into a time. 
- **history**: in PromptKit Stories, this Prompt type allows the user to go back to a certain point in a Story. For both manual and handsfree prompts, it displays a menu of available scenes to return to. More information on how history works can be found in the [PromptKit Story History](#promptkit-story-history) section. 
- **quickLook**: Displays the message in a Quick Look window for manual prompts. For handsfree prompts, the message is spoken back to the user. 
- **markdown**: Interprets the message as markdown. For manual prompts, it converts the markdown to HTML and displays a webpage to the user. For handsfree prompts, it converts the markdown to Rich Text and speaks it to the user. 
- **html**: Interprets the message as HTML, converts it to a webpage and displays in a Quick Look window or Safari window. Specify `useSafari` to true to open the URL in Safari. 
- **url**: Opens a Quick Look window or Safari to the supplies URL. Specify `useSafari` to true to open the URL in Safari. 
- **alert**: Displays the message in a modal alert dialog for manual prompts. If specified, the `title` of the prompt will be used as the title of the alert. Otherwise “PromptKit” will be used. Tapping OK will continue the execution of PromptKit. Tapping Cancel will terminate the shortcut. For handsfree prompts, the message is spoken to the user. 
- **notification**: Displays the message in a notification banner with manual driven prompts. If specified, the `title` of the prompt will be used as the title of the notification. Otherwise “PromptKit” will be used. Specify `notificationSound` to true to display a sound during the notification (default is no sound). For handsfree prompts, the message is spoken to the user. 
- **result**: Displays the message in a modal dialog for manual prompts. For handsfree prompts, the message is spoken to the user. 
- **none**: No message is displayed to the user. This type is used commonly in PromptKit Stories as a separator between scenes. 

Voice-driven prompts can specify the `speakChoices` option to verbally list out the choices after speaking the message. 

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
If you said, “I really like brownies.” and the `choices` has the following:

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

PromptKit will look if your input contains any words in any of the choices. In this case, the third choice would match your input and the response returned would be “brownie”.

On the other hand, if you entered, “While I enjoy a good piece of cake, I really prefer brownies,” PromptKit will choose and return cake since it was the first keyword match. PromptKit does not perform any complicated analysis of your input. If you desire this, consider [sending the input to a shortcut](#shortcuts). 

#### equals
Using the example above, “I really like brownies,” would not match any of the choices. You would have to say, “brownies” or “brownie” in order to match the brownies choice. Input is lowercase for string comparison purposes. 

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

<span id=“repeat”></span> 
### repeat
(Optional) Number
You can specify how many times PromptKit will ask the user your question. The default is 5. If at the end of the repeat loop, the user still has not answered the question, the ❓ string will be returned in the [**Response Dictionary**](#response-dictionary).

<span id=“spokenLanguage”></span> 
### spokenLanguage 
(Optional) Text
Setting the language will determine the language used to speak the prompt’s message. It also controls how the Yes, No, and Cancel choices in Confirm prompts are displayed.

The format of the dictation language is (language code)-(language region). For instance:

- **en-US**: English (USA)
- **en-GB**: English (United Kingdom)
- **fr-FR**: French (France)

<span id=“dictationLanguage”></span> 
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

### Additional Options

<span id=“speakChoices”></span> 
#### speakChoices
If a prompt type has a list of possible choices, setting this value to true in the Prompt Dictionary will cause PromptKit to list out the choices audibly in `handsfree` mode. 

<span id=“hideFromHistory”></span> 
#### hideFromHistory
For use with PromptKit Scenes and Stories, this will prevent the scene from being added to the history list. 

<span id=“notificationPlaySound”></span>
#### notificationPlaySound
For notification prompts, setting this value to true will play a sound when the notification banner appears. 

<span id=“alertShowCancel”></span>
#### alertShowCancel
For alert prompts, this will add the Cancel button to the alert. 

NOTE: Tapping Cancel will terminate shortcut execution. 

<span id=“confirmShowCancel”></span>
#### confirmShowCancel
For confirm prompts, this adds a PromptKit Cancel 🛑 option. Choosing this allows developers to handle cases other than Yes or No. 

<span id=“allowTranslationDictation”></span>
#### allowTranslationDictation
When Auto Translate is on, it may be difficult to translate the list of possible choices into the translation language. Some words may not translate very well, for instance. By default, PromptKit will switch to `manual` mode and raise dialogs and menus when Auto Translate is active. 

Setting `allowTranslationDictation` to true allows your handsfree prompt to continue in handsfree mode. Possible responses will be translated and be available, along with the original responses. For instance:

- Driving | Car | Drive | Auto

Will gain additional matching responses in French:

- La conduite | Voiture | Disque dur | auto

As you can see, the translation performed by Microsoft Cognitive Services sometimes makes mistakes. 

Remember that you can specify multiple modes in the mode attribute by separating the modes with a | character. If you set your mode to handsfree, you may want to consider supplying a manual mode at the end:

`"mode": "handsfree | handsfree | manual"`

For the first two attempts, handsfree mode will be used. Afterwards, manual mode will be employed. 

<span id=“returnResponseOnly”></span>
#### returnResponseOnly
By default, PromptKit returns the response chosen by the system. Setting this flag to false will return the entire PromptKit Response Dictionary. 

***

## Response Dictionary
If `returnResponseOnly` is false, PromptKit will return a PromptKit Response Dictionary. This dictionary contains more information about the PromptKit interaction the user had with your shortcut. It includes the following components:

- **response**: The accepted response from the user or one of control emoji symbols, such as 🛑 or ❓.
- **responses**: Each response from the user is recorded in this array.
- **original**: What the user said (as interpreted by iOS) to produce the Response value.
- **lowercase**: A lowercased version of the response. 
- **cleaned**: the response stripped of whitespace from the beginning and end of the response. 
- **repeatIndex**: The index from the repeat loop when PromptKit exited.

### Understanding the Emoji Symbols in Responses
If the response contains the following emoji symbols, you should interpret the response as follows:

🛑
The user spoke one of the Cancel phrases.

❓
The user did not speak anything that led to a successful response.

1
The user spoke one of the YES phrases. Used with the `Confirm` prompts.

0
The user spoke one of the NO phrases. Used with the `Confirm`  prompts.

Your shortcut should handle each of these cases for completeness. 

<span id=“promptkit-story”></span>
## PromptKit Story
A PromptKit Story is a collection of related PromptKit Prompts. A story can be used to create an interactive series of prompts. 

<span id=“promptkit-story”></span>
### PromptKit Story History


## Calling External Shortcut Shortcuts

### Terminating PromptKit From A Shortcut
If your external shortcut returns ⏹⏹⏹ to PromptKit, execution will stop in the current story.

<span id=“language-codes”></span>
### Language Codes
- **ar-SA**: Arabic (Saudi Arabia)
- **zh-CN**: Chinese (China)
- **zh-HK**: Chinese (Hong Kong [China])
- **zh-TW**: Chinese (Taiwan)
- **cs-CZ**: Czech (Czechia)
- **da-DK**: Danish (Denmark)
- **nl-BE**: Dutch (Belgium)
- **nl-NL**: Dutch (Netherlands)
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
- **ro-RO**: Romanian (Romania)
- **ru-RU**: Russian (Russia)
- **sk-SK**: Slovak (Slovakia)
- **es-MX**: Spanish (Mexico)
- **sv-SE**: Swedish (Sweden)
- **th-TH**: Thai (Thailand)
- **tr-TR**: Turkish (Turkey)

****

<span id="localization"></span> 
## Localization
PromptKit is available in English, but the application is fully ready to be localized. Use the Localization Helper shortcut to assist with localizing PromptKit into your language.

> [**Download Localization Helper from RoutineHub &raquo;**](https://routinehub.co/shortcut/1931)

- When the localization file is complete, submit a pull request on [the Record Text to Speech GitHub page](https://github.com/adamtow/promptkit).

You can also inspect the files for each supported language's language dictionary in the `localization` directory. This contains information such as alternate phrases for Yes, No, and Cancel, numbers, localized version of support translation languages (for the Translate Text with Microsoft action), and more. Help make PromptKit more accurate and more universal for all iOS users!

****

<span id="app-framework"></span>
## App Framework
GeoCuts was developed using the [Shortcut App Framework](https://routinehub.co/shortcut/1510) approach to developing application-like shortcuts. This framework was also used to develop:

- [**Cronios**](https://routinehub.co/shortcut/1267): The shortcuts scheduler for iOS.
- [**Inspector**](https://routinehub.co/shortcut/1106): View and modify objects at runtime in your shortcuts.
- [**LaunchCuts**](https://routinehub.co/shortcut/959): Folders and tags for your organizing and launching your shortcuts.
- [**WatchCuts**](https://routinehub.co/shortcut/1864): Trigger shortcuts on your iPhone and iPad using any of your iCloud-connected devices: iPhone, iPad, Mac, Apple Watch, or iCloud.com!

Learn more how you can create your own [shortcut applications with App Framework here](https://tow.com/shortcuts/framework).

****

<span id="troubleshooting"></span> 
## Troubleshooting

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
