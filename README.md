# Words-and-sentences-counter
import re

def count_words_and_sentences(text):
    
    # Strip leading and trailing spaces
    text = text.strip()
    
    # Count words
    words = text.split()
    word_count = len(words)
    
    # Count sentences (split by '.', '!', '?')
    sentences = re.split(r'[.!?]+', text)
    sentence_count = len([s for s in sentences if s.strip()])
    
    return word_count, sentence_count

def main():

    print("Welcome to the Word Counter Program!")
    user_input = input("Enter a sentence or paragraph: ")
    
    if not user_input.strip():
        print("Error: Input cannot be empty. Please enter some text.")
        return
    
    word_count, sentence_count = count_words_and_sentences(user_input)
    print(f"Word Count: {word_count}")
    print(f"Sentence Count: {sentence_count}")

if __name__ == "__main__":
    main()
