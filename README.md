# Morse Code Dictionary
MORSE_CODE_DICT = {
    'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 'F': '..-.', 'G': '--.',
    'H': '....', 'I': '..', 'J': '.---', 'K': '-.-', 'L': '.-..', 'M': '--', 'N': '-.',
    'O': '---', 'P': '.--.', 'Q': '--.-', 'R': '.-.', 'S': '...', 'T': '-', 'U': '..-',
    'V': '...-', 'W': '.--', 'X': '-..-', 'Y': '-.--', 'Z': '--..',
    '0': '-----', '1': '.----', '2': '..---', '3': '...--', '4': '....-', '5': '.....',
    '6': '-....', '7': '--...', '8': '---..', '9': '----.', ' ': '/'
}

def text_to_morse(text):
    text = text.upper()
    morse_text = ''
    for char in text:
        if char in MORSE_CODE_DICT:
            morse_text += MORSE_CODE_DICT[char] + ' '
        else:
            morse_text += '? '  # For unrecognized characters
    return morse_text

def morse_to_text(morse):
    morse_list = morse.strip().split(' ')
    text = ''
    morse_to_char = {v: k for k, v in MORSE_CODE_DICT.items()}
    for morse_char in morse_list:
        if morse_char in morse_to_char:
            text += morse_to_char[morse_char]
        else:
            text += '?'  # For unrecognized Morse codes
    return text

# Example Usage
if __name__ == "__main__":
    choice = input("Enter '1' to convert text to Morse code, '2' to convert Morse code to text: ")
    if choice == '1':
        input_text = input("Enter the text to be converted: ")
        morse_text = text_to_morse(input_text)
        print("Morse code equivalent:", morse_text)
    elif choice == '2':
        input_morse = input("Enter the Morse code to be converted: ")
        text = morse_to_text(input_morse)
        print("Text equivalent:", text)
    else:
        print("Invalid choice!")

