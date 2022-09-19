# RSA-Factoring-Challenge

### Author :man_technologist:
Thaoban Abdrasheed :nerd_face:

## Acknowledgement :pray:
This project is designed to factorize as many numbers as possible into a product of two smaller numbers.
It works perfectly for that except the case of bignums (numbers bigger than long long unsigned integers)
please any contribution towards making this project works for bignums will be highly appreciated..

## Tasks :page_with_curl:

* ** 0. Factorize all the things!**
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
* ** 1. RSA Factoring Challenge**
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
