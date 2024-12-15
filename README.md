# morstranslater
Convert any sentence you want into Morse code using only English words and numbers
MORSE_ALPHABET = {
    'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 'F': '..-.', 'G': '--.',
    'H': '....', 'I': '..', 'J': '.---', 'K': '-.-', 'L': '.-..', 'M': '--', 'N': '-.',
    'O': '---', 'P': '.--.', 'Q': '--.-', 'R': '.-.', 'S': '...', 'T': '-', 'U': '..-',
    'V': '...-', 'W': '.--', 'X': '-..-', 'Y': '-.--', 'Z': '--..',
    '0': '-----', '1': '.----', '2': '..---', '3': '...--', '4': '....-', '5': '.....',
    '6': '-....', '7': '--...', '8': '---..', '9': '----.', ' ': '/'
}

def text_to_mors(text):
    text = text.upper()
    mors_text = ''
    for letter in text:
        if letter in MORSE_ALPHABET:
            mors_text += MORSE_ALPHABET[letter] + ' '
        else:
            mors_text += '? ' # for unidentified characters
    return mors_text
                



if __name__ == "__main__":
    entry_text = input("Enter the text to convert: ")
    mors_text =text_to_mors(entry_text)
    print("Morse code equivalent:", mors_text)
