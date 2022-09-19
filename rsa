#!/usr/bin/python3


from fractions import gcd
from sys import argv


def pollards_rho(n):
    x = 2
    y = 2
    d = 1
    f = lambda x: (x**2 + 1) % n
    while d == 1:
        x = f(x)
        y = f(f(y))
        d = gcd(abs(x - y), n)
    if d != n:
        return d


def read_file():
    with open(argv[1]) as f:
        for number in f:
            num = int(number)
            if num % 2 == 0:
                print("{:d}={}*{}".format(num, num // 2, 2))
            else:
                p = pollards_rho(num)
                f1 = p
                f2 = int(num / p)
                print("{}={}*{}".format(num, f1, f2))


if __name__ == "__main__":
    read_file()
