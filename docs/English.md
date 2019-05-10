# PromptKit
PromptKit is a shortcut library for creating powerful, interactive, multilingual prompts featuring speech, dictation, menus, and dialogs.

With PromptKit, you can:

- Select between voice or dialog-driven prompts. Not connected to the internet? Your voice-driven prompts will automatically turn into menu and dialog prompts. 
- Automatically translate prompts from one language to another. 
- Restrict your prompts to accept a list of answers.
- Use comparison operators such as contains, equals, greater than, less than, before, after and between for text, number, date and time input.
- Configure the number of times a prompt can be repeated if a decision was not chosen. 
- Confirmations with yes or no.
- Asking for numeric input.
- Freefrom voice input.
- Cancellation by the user.
- No response or accepted response from the user.



## PromptKit Dictionary
PromptKit supports text and dictionary input. Specifying the PromptKit Dictionary gives you the most control over the look and feel of your prompt.

## PromptKit Stories
A PromptKit Story is collection of PromptKit Prompts forms the basis of a PromptKit Story. A story can be build to create simple or complex interactive voice or menu-driven experiences on iOS. PromptKit dictionaries that belong to a story have additional optional attributes. 

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
- [decisions](#decisions)
- [spokenLanguage](#spokenLanguage)
- [dictationLanguage](#dictationLanguage)
- [repeat](#repeat)
- [comparison](#comparison)
- [speakChoices](#decisions)
- [hideFromHistory](#hideFromHistory)
- [dataKey](#dataKey)

### message (Required) Text or Array
This is the text displayed or spoken to the user. If you supply just one string, it will be used for all repetitions. If you supply multiple strings in an array, the string used will correspond to the loop repeat index. For instance:

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
Specifies how the message will be interpreted and presented to the user. Valid values are:

- **text** (default): For manual prompts, the message is displayed in an Ask For Input action dialogue. For handsfree prompts, the message is spoken to the user and Dictate Text Action is used to capture the user’s input. This type can be combined with the `choices` array to accept only certain responses.
- **confirm**: Prompts the user for a Yes or No response.
- **number**: Prompts the user to enter a number. Verifies that the user entered a valid number. 
- **list**: Prompts the user to choose from a list of choices.
- **date**: Prompts the user to enter a date. Manual prompts will display the standard iOS Date picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date. 
- **dateTime**: Prompts the user to enter a date and time. Manual prompts will display the standard iOS Date and Time picker. Voice prompts will use the Get Dates From Input action to convert dictated text into a date and time. 
- **time**: Prompts the user to enter a time. Manual prompts will display the standard iOS Time picker. Voice prompts will use the Get Dates From Input and Format Dates actions to convert dictated text into a time. 
- **history**: in PromptKit Stories, this Prompt type allows the user to go back to a certain point in a Story. For both manual and handsfree prompts, it displays a menu of available scenes to return to. More information on how history works can be found in the [PromptKit Story History](#promptkit-Story-History) section. 
- **quickLook**: Displays the message in a Quick Look window for manual prompts. For handsfree prompts, the message is spoken back to the user. 
- **markdown**: Interprets the message as markdown. For manual prompts, it converts the markdown to HTML and displays a webpage to the user. For handsfree prompts, it converts the markdown to Rich Text and speaks it to the user. 
- **html**: Interprets the message as HTML, converts it to a webpage and displays in a Quick Look window. 
- **http**: Opens a Quick Look window for manual prompts. Opens Safari for handsfree prompts and returns the user back to the Shortcuts app to continue execution. 
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

### comparison (Optional) String
By default, your response will be matched to possible answers in the `choices` array using a contains comparison. You can specify the following values for `comparison`:

- contains (default for text)
- equals (default for numbers)
- exact
- greaterThan (numbers only)
- lessThan (numbers only)
- between (numbers only)

**Note**: *PromptKit currently does not support using comparison operators with the date, dateTime, and time prompt types. *

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
For use with numbers, the input must be between any of the numbers in items within the `choices` array. Use the `-` character as a delimiter between the lower and upper bounds. For instance:

`"choices": "1-10 | 20-30"`


****


## 🛑 (Optional) Text
This text is spoken to the user if the Cancel keyword phrase is spoke. If not included in the Prompt Dictionary, nothing will be spoken.

## ❓(Optional) Text
This text is spoken to the user if no successful response was captured. If not included in the Prompt Dictionary, nothing will be spoken.

<span id=“repeat”></span> 
### repeat
(Optional) Number
You can specify how many times PromptKit will ask the user your question. The default is 5. If at the end of the repeat loop, the user still has not answered the question, the ❓ string will be returned in the [**Response Dictionary**](#response-dictionary).

<span id=“spokenLanguage”></span> 
### spokenLanguage 
(Optional) Text
Setting the language will determine the language used to speak the prompt’s message. It also controls how the Yes, No, and Cancel choices in confirm prompts are displayed.

The format of the dictation language is (language code)-(language region). For instance:

- en-US: English (USA)
- en-GB: English (United Kingdom)
- fr-FR: French (France)

A complete list of [supported languages and codes](#language-codes) can be found here. 

<span id=“dictationLanguage”></span> 
### dictationLanguage 
(Optional) Text
Setting the dictationLanguage will determine how Dictate Text Action interprets user input. If not specified, the dictation language will be the same as the spoken language. 

The format of the dictation language is the same as for spokenLanguage. 

***

## Response Dictionary
The Response Dictionary is what PromptKit returns to your shortcut. It had the following components:

- **response**: The accepted response from the user or one of the four emoji symbols: 🛑, 👍, 👎, or ❓.
- **responses**: Each response from the user is recorded in this array.
- **original**: What the user said (as interpreted by iOS) to produce the Response value.
- **repeatIndex**: The index from the repeat loop when PromptKit exited.

### Understanding the Emoji Symbols in Responses
If the response contained of the four emoji symbols, you should interpret the response as follows:

🛑
The user spoke one of the Cancel phrases.

❓
The user did not speak anything that led to a successful response.

👍
The user spoke one of the YES phrases. Used with the `Confirm` prompts.

👎
The user spoke one of the NO phrases. Used with the `Confirm`  prompts.

Your shortcut should handle each of these cases for completeness. 

<span id=“promptkit-Story-history”></span>
### PromptKit Story History


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
