# Efficient Identification of Primes

This brief paper describes a robust pattern of prime numbers and explains how to use that pattern to efficiently identify primes. Examples are provided throughout the text. An additional data file containing the first one million primes is also provided in comma-separated (CSV) format.

## Introduction

Prime numbers can be used for unique measurement because the way that they alter information is guaranteed not to overlap with other numbers. While conducting research and experimentation regarding quantum computing and this use of primes, a pattern matching the position of prime numbers on the number line became apparent.

The full set of numbers matching the pattern includes more than just primes, but every number in the set is related only to primes. A descriptive label for the entire set has not yet become apparent to me, but perhaps it will be apparent to someone else.

As a short note, some of what I have noticed thus far in the pattern and the numbers it produces is that it appears to be a navigable structure providing unique information encodings and translation intersections across those encodings. And it provides an ever-growing information space sufficient for including the complexities of the number line period to which it belongs.

This pattern should assist with many prime number operations, including identifying primes and performing primality testing against arbitrary numbers.

The terminology and notation that I use in this paper may be unconventional. This work is one part of a collection of efforts regarding dynamic quantization, differentiation, and other concepts. Further works are forthcoming and I am, of course, appreciative of collaboration or correction.

The additional data file will hopefully be useful for anyone interested in looking at the pattern. My goal for the paper itself has been to make it possible for anyone with a modest amount of mathematics familiarity to explore for themselves immediately.

## Number Base Encoding

One straightforward way to expose the pattern is to use the digits that our familiar integers of the number line (regular numbers) would have if they were translated into different number bases. The standard number base that we use every day is base 10. That means we have ten unique symbols (0 - 9) which are used to represent all number values.

The part that matters for this explanation is the last digit when a number is translated into a particular number base. This last digit is also the modulus value for a number when measured against the base number. So the modulus calculation is all we need here.

The base number defines how many symbols are available to represent values. We always start with 0 as the first symbol, so base 3 would have 0, 1, and 2 as the available symbols. Building upon that, base 4 would have 0, 1, 2, and 3 as the set of possible symbols.

When we reach the last symbol in any number base and then add one to move to the next number, we put a zero for the last digit and add 1 to the digit next to it on the left. We do this habitually in base 10.

If we only concern ourselves with the last digit, then as we move along the number line in any number base, we see an endless repeating pattern of the symbols of that number base. The following table shows the last digit of a short sequence of numbers in different bases from base 2 through base 12. The standard base 10 version of the numbers are on the left.

| Number | Base2 | Base3 | Base4 | Base5 | Base6 | Base7 | Base8 | Base9 | Base10 | Base11 | Base12 |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 3 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 4 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 5 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 6 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 7 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 8 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 9 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 10 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 11 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 12 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 13 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 14 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 15 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 16 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 17 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 18 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 19 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 20 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |



