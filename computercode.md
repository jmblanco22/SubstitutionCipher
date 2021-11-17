# Encoding the Substitution cipher
---
`def translate(startLetters, endLetters, spot):
    #find the letter at (spot) in the startLetters string. 
  
    #find the location of the letter in the endLetters string.
  return endLetters.find(startLetters[spot])
  
def rotate(alphabet):
    #move the first letter of the alphabet to the end
    #shift all the letters
  return alphabet[1:]+alphabet[0]

def main():
  alpha1 = "abcdefghijklmnopqrstuvwxyz"
  alpha2 = "zyxwvutsrqponmlkjihgfedcba"
  #make the two alphabets for substitution

  message = input("give a message: ") #message
  letter = message[0] #array for loop in message
  encoded = "" #will print the encoded version
  for letter in message:
    if alpha1.find(letter) >= 0:
      # Find location of letter in alphabet
      pos = alpha1.find(letter)

        #pass this letter through alpha2
      pos = translate(alpha1, alpha2, pos) #starting, ending, current position
        #Translate back from position to a letter
      encoded += alpha1[pos]
      alpha2 = rotate(alpha2)
  print(encoded)`
  
  main()
  
  ---
  # decoding the substitution cipher
  ---
  `def translate(startLetters, endLetters, spot):
    #find the letter at (spot) in the startLetters string. 
  
    #find the location of the letter in the endLetters string.
  return endLetters.find(startLetters[spot])
  
def rotate(alphabet):
    #move the first letter of the alphabet to the end
    #shift all the letters
  return alphabet[1:]+alphabet[0]

def main():
  alpha2 = "zyxwvutsrqponmlkjihgfedcba"
  alpha1 = "abcdefghijklmnopqrstuvwxyz"
  
  #make the two alphabets for substitution

  encoded = ("qkfsncfi") #encoded
  letter = encoded[0] #array for loop in message
  message = "" #will print the message version
  for letter in encoded:
    if alpha1.find(letter) >= 0:
      # Find location of letter in alphabet
      pos = alpha1.find(letter)

        #pass this letter through alpha2
      pos = translate(alpha1, alpha2, pos) #starting, ending, current position
        #Translate back from position to a letter
      message += alpha1[pos]
      alpha2 = rotate(alpha2)
  print(message) 
main()`



