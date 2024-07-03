# Text-To-Speech-Converter
This micro project, created using HTML, CSS, and JavaScript, takes any written input from the user and successfully converts it to speech utilizing the audio services available on the device.

The provided HTML, CSS, and JavaScript code together create a simple Text-to-Speech (TTS) converter web application. Here's a detailed breakdown of each part and how they work together:

**HTML Code**

The HTML code defines the structure of the web page.
    <head>:               Contains metadata about the document, such as the character set, viewport settings, title, and a link to an external CSS file.
    <body>:               Contains the main content of the page.
    <div class="hero">:   A container for the hero section, which holds the main interactive elements of the page.
    <h1>:                 The main heading with a span for styling a part of the text.
    <textarea>:           An input area for the user to write text.
    <div class="row">:    A container for the row elements.
    <select>:             A dropdown menu for selecting different voices.
    <button>:             A button that triggers the TTS functionality. It contains an image to visually indicate its purpose.


**CSS Code**

The CSS code styles the HTML elements, enhancing the visual presentation.
    Universal selector *:   Resets the margin and padding of all elements to 0, sets the font to 'Poppins', and ensures all elements follow the border-box box-sizing model.
    .hero:                  Styles the hero section to take full width and height, with a linear gradient background, center alignment, and white text color.
                            h1 and h1 span: Styles the main heading and its span.
    textarea:               Styles the text area input.
    textarea::placeholder:  Styles the placeholder text in the textarea.
    .row:                   Styles the row container.
    button:                 Styles the button.
    button img:             Styles the image inside the button.
    select:                 Styles the dropdown menu.


**JavaScript Code**

The JavaScript code handles the functionality of the TTS converter.
          let speech = new SpeechSynthesisUtterance();:                                        Creates a new instance of SpeechSynthesisUtterance, which represents the speech request.
          let voices = [];:                                                                    Initializes an empty array to hold the available voices.
          let voiceSelect = document.querySelector("select");:                                 Selects the dropdown menu element.
    Handling Voices
          window.speechSynthesis.onvoiceschanged:                                              An event handler that triggers when the list of available voices changes.
          voices = window.speechSynthesis.getVoices();:                                        Retrieves the available voices.
          speech.voice = voices[0];:                                                           Sets the initial voice to the first available voice.
          voices.forEach((voice, i) => (voiceSelect.options[i] = new Option(voice.name, i)));: Populates the dropdown menu with the available voices.
    Changing the Voice
          voiceSelect.addEventListener("change", () => { ... });:                              An event listener that changes the voice based on the user's selection from the dropdown menu.
          speech.voice = voices[voiceSelect.value];:                                           Updates the speech object's voice property with the selected voice.
    Handling Button Click
          document.querySelector("button").addEventListener("click", () => { ... });:          An event listener that triggers the speech synthesis when the button is clicked.
          speech.text = document.querySelector("textarea").value;:                             Sets the text to be spoken from the textarea's value.
          window.speechSynthesis.speak(speech);:                                               Initiates the speech synthesis with the set properties.


**Summary**

HTML: Structures the web page with a heading, a textarea for text input, a dropdown for voice selection, and a button to start the speech synthesis.
CSS: Styles the web page elements, making it visually appealing and user-friendly.
JavaScript: Handles the text-to-speech functionality:
Retrieves available voices and populates the dropdown.
Changes the speech voice based on user selection.
Reads aloud the text from the textarea when the button is clicked.
By combining these three components, the application allows users to input text, select a voice, and hear the spoken version of the input text.

