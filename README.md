# RSA-Factoring-Challenge

![RSA-Image](images/RSA-img.JPG)

## Description

This project is designed to factorize as many numbers as possible into a product of two smaller numbers.
It works perfectly for that except the case of bignums (numbers bigger than long long unsigned integers)
please any contribution towards making this project work for bignums will be highly appreciated.

## Information

- HTTPS uses Secure Socket Layer to encrypt data that is transferred between client and server. SSL uses the RSA algorithm, an asymmetric encryption technology. The precise details of how the algorithm works is complex, but basically it leverages the fact that whilst multiplying two large prime numbers together is easy, factoring the result back into the constituent primes is very, very hard. How all SSL/RSA encryption works is:

- The server generates two large prime numbers, and multiplies them together. This is called the "public key". This key is made available to any client which wishes to transmit data securely to the server. The client uses this "public key" to encrypt data it wishes to send. Now because this is an asymmetric algorithm, the public key cannot be used to decrypt the transmitted data, only encrypt it. In order to decrypt, you need the original prime numbers, and only the server has these (the "private key"). On receiving the encrypted data, the server uses its private key to decrypt the transmission.

- In the case of you browsing the web, your browser gives the server its public key. The server uses this key to encrypt data to be sent to your browser, which then uses its private key to decrypt.

- So yes all data transmitted to/from server over HTTPs is encrypted and encrypted well. Typical SSL implementations use 128 or 256 digits for their keys. To break this you need a truly vast amount of computing resources.

## Tasks

- ### 0. Factorize all the things!

```
Factorize as many numbers as possible into a product of two smaller numbers.

	Usage: factors <file>
		where <file> is a file containing natural numbers to factor.
	Output format: n=p*q
		one factorization per line
		p and q don’t have to be prime numbers

	julien@ubuntu:~/factors$ cat tests/test00
	4
	12
	34
	128
	1024
	4958
	1718944270642558716715
	9
	99
	999
	9999
	9797973
	49
	239809320265259
	julien@ubuntu:~/factors$ time ./factors tests/test00
	4=2*2
	12=6*2
	34=17*2
	128=64*2
	1024=512*2
	4958=2479*2
	1718944270642558716715=343788854128511743343*5
	9=3*3
	99=33*3
	999=333*3
	9999=3333*3
	9797973=3265991*3
	49=7*7
	239809320265259=15485783*15485773

	real    0m0.009s
	user    0m0.008s
	sys 0m0.001s
```

- ### 1. RSA Factoring Challenge

```
	RSA Laboratories states that: for each RSA number n, there exist prime numbers p and q such that

	n = p × q. The problem is to find these two primes, given only n.

	This task is the same as task 0, except:

	p and q are always prime numbers
	There is only one number in the files
	julien@ubuntu:~/RSA Factoring Challenge$ cat tests/rsa-1
	6
	julien@ubuntu:~/RSA Factoring Challenge$ ./rsa tests/rsa-1
	6=3*2
	julien@ubuntu:~/RSA Factoring Challenge$ cat tests/rsa-2
	77
```

## Author

[David Atat](www.github.com/daveeazi)

## Resources

- [RSA](<https://en.wikipedia.org/wiki/RSA_(cryptosystem%29)>)
- [How does HTTPS provide security?](https://stackoverflow.com/questions/3968095/how-does-https-provide-security)
- [Prime Factorization](https://privacycanada.net/mathematics/prime-factorization/)
