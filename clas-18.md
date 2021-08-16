# Cryptography

## Encryption, Decryption & Hacking 

### Encrypting a message 

***The Caesar Cipher is a simple substitution cipher that replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.***

**To make the encrypted message above, I shifted the alphabet by 6 and used this substitution table:** 

        A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z
        G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z	A	B	C	D	E	F

### Decrypting a message 

***Caesar always used a shift of 3. As long as his message recipient knew the shift amount, it was trivial for them to decode the message.***

**The comrade uses this substitution table, where the alphabet is shifted by 3:** 

        A	B	C	D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z
        D	E	F	G	H	I	J	K	L	M	N	O	P	Q	R	S	T	U	V	W	X	Y	Z	A	B	C

### Cracking the cipher 

***There are three main techniques he could use: frequency analysis, known plaintext, and brute force.***

* Frequency analysis 

*Human languages tend to use some letters more than others. For example, "E" is the most popular letter in the English language. We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.*

* Known plaintext 

*Another term for the original unencrypted message is plaintext. If the enemy already knew some part of the plaintext, it will be easier for them to crack the rest of the encrypted version.*

* Brute force 

*There are only 25 possible shifts. The enemy could take some time to try out each of them and find one that yielded a sensible message. They wouldn't even need to try the shifts on the entire message, just the first word or two.* 

## Ceasar Cipher 

***In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.***

***The encryption step performed by a Caesar cipher is often incorporated as part of more complex schemes, such as the Vigenère cipher, and still has modern application in the ROT13 system. As with all single-alphabet substitution ciphers, the Caesar cipher is easily broken and in modern practice offers essentially no communications security.***

***Deciphering is done in reverse, with a right shift of 3.***

***The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme.***

## Cryptography Crash Course 

***The process of making text secret is called encryption***

***The reverse process is called decryption***

