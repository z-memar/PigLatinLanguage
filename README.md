# PigLatinLanguage
print(" Zahra Memar",'\n',"Homework#3",'\n',"September 25,2019")
print("")

import string
VOWEL=['a','e','i','o','u']
piglet_vowel='hay'
piglet_constant='ay'

def AskUserForSentences():
    while True:
        try:
            sentence= str(input('''Please input a sentence that contains three words
    and spaces, Or type "Quit" to exist the program: '''))
            if sentence=='Quit':
                break
            sentence_lowercase = LowercaseSentence(sentence)
            split_sentence=SplitSentenceIntoList(sentence_lowercase)
            if len(split_sentence)==3:
                    piglatin_word=ConvertWrodToPigLatin(split_sentence)
                    PrintThreeWordPhrase(piglatin_word)
            else:
                print('''Error!, your sentence 
                     includes less or more than three words.  ''')
        except ValueError:
            print("Error!your input is not a string sentence.")

def LowercaseSentence(sentence):
    sentence_lowercase = sentence.lower()
    print(sentence_lowercase)
    return sentence_lowercase

def SplitSentenceIntoList(sentence_lowercase):
    split_sentence = (sentence_lowercase).split()
    print(split_sentence)
    return split_sentence
    
def ConvertWrodToPigLatin(split_sentence):
    piglatin_word=[]
    for x in range(3):
        word=split_sentence[x]
        letter=word[0]
        if letter in VOWEL:
            piglatin_word.append(word[:] + piglet_vowel)   
        else:
            piglatin_word.append(word[1:]+word[0]+piglet_constant)
    return piglatin_word

def PrintThreeWordPhrase(piglatin_word):
     print(piglatin_word[0],piglatin_word[1],piglatin_word[2])
     print("***")
AskUserForSentences()
