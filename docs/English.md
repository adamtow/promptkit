# PromptKit
PromptKit is a shortcut library for asking the user for input using voice. PromptKit handles:

- Repeating the question.
- Restricting the accepted response to a set of possible answers.
- Confirmations with YES or NO.
- Asking for numeric input.
- Freefrom voice input.
- Cancellation by the user.
- No response or accepted response from the user.

## PromptKit Dictionary
PromptKit supports text and dictionary input. Specifying the PromptKit Dictionary gives you the most control over the question and dictation process. The following elements comprise a valid PromptKit dictionary:

- [Question](#question)
- [Type](#type)
- [Answers](#answers)
- [Contains](#contains)
- [Cancel](#cancel)
- [No Choice](#no-choice)
- [Repetitions](#repetitions)
- [Language](#language)

### Question
(Required) Text or Array
This is the text spoken to the user prior to dictation. If you supply just one string, it will be used for all repetitions. If you supply multiple strings in an array, the string used will correspond to the loop repeat index. For instance:

```
Question:
	[
		"Pick a number between 1 and 5.",
		"Any number between 1 and 5.",
		"It's not that hard, choose a number between 1 and 5.",
		"1. 2. 3. 4. or 5. Come on now."
	]
```

The first time PromptKit is called, it will speak the first question string. If a successful response is not given, it will speak the second question, followed by the third and fourth. If the user did not provide a successful response after the fourth, the function will return with a ❓ response.

## Type
(Required) Text 
Specifies the type of question being asked. Valid values are currently:

- **Freeform**: Prompts the user to input arbitrary text. Can be combined with the Answers array to restrict the response to a series of possible answers.
- **Confirm**: Prompts the user for a Yes or No response.
- **Number**: Prompts the user to enter a number. Verifies that the user entered a valid number. 

## Answers
(Optional) Array
If specified, the response will be compared with the values in the Answers array. Each value in the array can have optional matching strings, delimited by the | character. For instance:

```
{
	"Question": "What mapping application would you like to use?",
	"Answers":
		[
			"Maps|Apple Maps|Apple",
			"Google Maps"|"Google",
			"Waze"
		]
}
```

When run, the user will be prompted to choose a default maps app. The user could say "Maps", "Apple Maps", or "Apple" in order to select the "Maps" choice. For "Google Maps", the only two choices are "Google Maps" and "Google". "Waze" is the only choice for the final answer.

You can use the | delimiter with both Freeform and Number prompts. Confirm prompts make use of the Localized Strings dictionary to determine yes or no responses.

## Contains
(Optional) Boolean
If specified and true, the comparison operator used to evaluate each string in the Answers array for Freeform prompts will be CONTAINS. If false or not specified, EQUALS will be the comparison operator.

## Cancel
(Optional) Text
This text is spoken to the user if the Cancel keyword phrase is spoke. If not included in the Prompt Dictionary, nothing will be spoken.

## No Choice
(Optional) Text
This text is spoken to the user if no successful response was captured. If not included in the Prompt Dictionary, nothing will be spoken.

## Repetitions
(Optional) Number
You can specify how many times PromptKit will ask the user your question. The default is 5. If at the end of the repeat loop, the user still has not answered the question, the ❓ string will be returned in the [**Response Dictionary**](#response-dictionary).

## Language
(Optional) Text
Setting the language will switch what strings are interpreted as YES, NO, and CANCEL responses.

>Right now, setting the Language in the prompt dictionary **does not** change the voice used by Speak Text and Dictation. I'm looking into a way to get this to work properly.

***

## Response Dictionary
The Response Dictionary is what PromptKit returns to your shortcut. It had the following components:

- **Response**: The accepted response from the user or one of the four emoji symbols: 🛑, 👍, 👎, or ❓.
- **Responses**: Each response from the user is recorded in this array.
- **Original**: What the user said (as interpreted by iOS) to produce the Response value.
- **Question**: The Question object from the PromptKit Dictionary.
- **Repeat Index**: The index from the repeat loop when PromptKit exited.

### Understanding the Emoji Symbols
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
