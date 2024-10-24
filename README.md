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

If we only concern ourselves with the last digit, then as we move along the number line in any number base, we see an endless repeating pattern of the symbols of that number base. The following table shows the last digit of a short sequence of numbers in different bases from base 2 through base 10. The standard base 10 version of the numbers are on the left for reference.

| Number | Base2 | Base3 | Base4 | Base5 | Base6 | Base7 | Base8 | Base9 | Base10 |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| **0** | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| **1** | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| **2** | 0 | 2 | 2 | 2 | 2 | 2 | 2 | 2 | 2 |
| **3** | 1 | 0 | 3 | 3 | 3 | 3 | 3 | 3 | 3 |
| **4** | 0 | 1 | 0 | 4 | 4 | 4 | 4 | 4 | 4 |
| **5** | 1 | 2 | 1 | 0 | 5 | 5 | 5 | 5 | 5 |
| **6** | 0 | 0 | 2 | 1 | 0 | 6 | 6 | 6 | 6 |
| **7** | 1 | 1 | 3 | 2 | 1 | 0 | 7 | 7 | 7 |
| **8** | 0 | 2 | 0 | 3 | 2 | 1 | 0 | 8 | 8 |
| **9** | 1 | 0 | 1 | 4 | 3 | 2 | 1 | 0 | 9 |
| **10** | 0 | 1 | 2 | 0 | 4 | 3 | 2 | 1 | 0 |
| **11** | 1 | 2 | 3 | 1 | 5 | 4 | 3 | 2 | 1 |
| **12** | 0 | 0 | 0 | 2 | 0 | 5 | 4 | 3 | 2 |
| **13** | 1 | 1 | 1 | 3 | 1 | 6 | 5 | 4 | 3 |
| **14** | 0 | 2 | 2 | 4 | 2 | 0 | 6 | 5 | 4 |
| **15** | 1 | 0 | 3 | 0 | 3 | 1 | 7 | 6 | 5 |
| **16** | 0 | 1 | 0 | 1 | 4 | 2 | 0 | 7 | 6 |
| **17** | 1 | 2 | 1 | 2 | 5 | 3 | 1 | 8 | 7 |
| **18** | 0 | 0 | 2 | 3 | 0 | 4 | 2 | 0 | 8 |
| **19** | 1 | 1 | 3 | 4 | 1 | 5 | 3 | 1 | 9 |
| **20** | 0 | 2 | 0 | 0 | 2 | 6 | 4 | 2 | 0 |

## Composite Codes From Bases 3, 6, and 8

If we combine the last digit values for base 3, base 6, and base 8 by listing them in a sequence, then we have a three-digit composite code for every number. The number doesn't change, of course, but this code gives us a useful alternative view of some information that was already contained within the number. It's a different way of looking at any number. For the rest of this paper, I'll use the notation B3:6:8 to refer to these three-digit codes and the codes themselves will just be three digit values and the zeroes will always be shown.

Using information from the table above, we can make the B3:6:8 code for the number 15 by putting together 0, 3, and 7 which are the values from the base 3, base 6, and base 8 columns. This gives us 037 as the B3:6:8 code for the number 15.

As another example, the B3:6:8 code for the number 4 would be 144.

The following table shows the B3:6:8 codes for a sequence of numbers from 0 through 30 with the last digit value from each base included as a reference for how the three-digit code was assembled.

| Number | Base3 | Base6 | Base8 | B3:6:8 Code |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| **0** | 0 | 0 | 0 | 000 |
| **1** | 1 | 1 | 1 | 111 |
| **2** | 2 | 2 | 2 | 222 |
| **3** | 0 | 3 | 3 | 033 |
| **4** | 1 | 4 | 4 | 144 |
| **5** | 2 | 5 | 5 | 255 |
| **6** | 0 | 0 | 6 | 006 |
| **7** | 1 | 1 | 7 | 117 |
| **8** | 2 | 2 | 0 | 220 |
| **9** | 0 | 3 | 1 | 031 |
| **10** | 1 | 4 | 2 | 142 |
| **11** | 2 | 5 | 3 | 253 |
| **12** | 0 | 0 | 4 | 004 |
| **13** | 1 | 1 | 5 | 115 |
| **14** | 2 | 2 | 6 | 226 |
| **15** | 0 | 3 | 7 | 037 |
| **16** | 1 | 4 | 0 | 140 |
| **17** | 2 | 5 | 1 | 251 |
| **18** | 0 | 0 | 2 | 002 |
| **19** | 1 | 1 | 3 | 113 |
| **20** | 2 | 2 | 4 | 224 |
| **21** | 0 | 3 | 5 | 035 |
| **22** | 1 | 4 | 6 | 146 |
| **23** | 2 | 5 | 7 | 257 |
| **24** | 0 | 0 | 0 | 000 |
| **25** | 1 | 1 | 1 | 111 |
| **26** | 2 | 2 | 2 | 222 |
| **27** | 0 | 3 | 3 | 033 |
| **28** | 1 | 4 | 4 | 144 |
| **29** | 2 | 5 | 5 | 255 |
| **30** | 0 | 0 | 6 | 006 |

## The Eight Codes of Primes

Every prime number will be one of these eight codes (111, 113, 115, 117, 251, 253, 255, or 257) with the exception of the numbers 2 and 3. The codes for those numbers are 222 and 033, respectively. Although both 2 and 3 fit the definition of a prime number, which is a number that cannot be divided by anything except the number 1 and itself, they are the only two primes that do not fit the pattern.

The numbers 2 and 3 are not needed to find primes nor to check if a number is prime. But 2 and 3, in the form of their product (`2 x 3 = 6`), do tell us how to efficiently move along the number line in order to follow the pattern. Additional details follow in the text below, of course.

**It is important to note that every prime number other than 2 and 3 will be one of these eight codes, but not every number that is one of these eight codes will be prime. Those numbers will all be something different but directly related to the primes, and they are also meaningful in the pattern.**

If we only concern ourselves with the numbers that have these eight codes, then we have a closed set. These numbers only relate to each other, and every number with one of the eight codes will be one of the following four types:

- a prime (such as `5`, `7`, `23`, `59`, etc.)
- a product of two or more primes (such as `35`, which is `5 x 7`)
- a prime raised to an exponent greater than one, which is a product of a prime with itself (such as `25`, which is `5²` or `5 x 5`)
- a product of two or more primes and at least one of them is also raised to an exponent greater than one (such as `175`, which is `7 x 25` or `7 x 5²`)

Because the entire set of numbers with these eight codes follows these rules, we can identify any number as prime if it is not one of the other three types, which are all combinations of only primes.

So if we exclude 2 and 3 and include 1, which happens automatically if we stick to only the set of numbers with the eight codes, then we only need to concern ourselves with how these numbers interact in order to identify all primes on the number line. The following table displays this view for numbers 0 through 144 and includes a note describing the calculation used to determine that a number with one of the eight codes is not prime.

| Number | B3:6:8 Code | Prime (Y/N) | Non-Prime Note |
| ----------- | ----------- | ----------- | ----------- |
| **0** |     |   |   |
| **1** | 111 | Y |   |
| **2** |     |   |   |
| **3** |     |   |   |
| **4** |     |   |   |
| **5** | 255 | Y |   |
| **6** |     |   |   |
| **7** | 117 | Y |   |
| **8** |     |   |   |
| **9** |     |   |   |
| **10** |     |   |   |
| **11** | 253 | Y |   |
| **12** |     |   |   |
| **13** | 115 | Y |   |
| **14** |     |   |   |
| **15** |     |   |   |
| **16** |     |   |   |
| **17** | 251 | Y |   |
| **18** |     |   |   |
| **19** | 113 | Y |   |
| **20** |     |   |   |
| **21** |     |   |   |
| **22** |     |   |   |
| **23** | 257 | Y |   |
| **24** |     |   |   |
| **25** | 111 | N | square (5²) |
| **26** |     |   |   |
| **27** |     |   |   |
| **28** |     |   |   |
| **29** | 255 | Y |   |
| **30** |     |   |   |
| **31** | 117 | Y |   |
| **32** |     |   |   |
| **33** |     |   |   |
| **34** |     |   |   |
| **35** | 253 | N | product (5 x 7) |
| **36** |     |   |   |
| **37** | 115 | Y |   |
| **38** |     |   |   |
| **39** |     |   |   |
| **40** |     |   |   |
| **41** | 251 | Y |   |
| **42** |     |   |   |
| **43** | 113 | Y |   |
| **44** |     |   |   |
| **45** |     |   |   |
| **46** |     |   |   |
| **47** | 257 | Y |   |
| **48** |     |   |   |
| **49** | 111 | N | square (7²) |
| **50** |     |   |   |
| **51** |     |   |   |
| **52** |     |   |   |
| **53** | 255 | Y |   |
| **54** |     |   |   |
| **55** | 117 | N | product (5 x 11) |
| **56** |     |   |   |
| **57** |     |   |   |
| **58** |     |   |   |
| **59** | 253 | Y |   |
| **60** |     |   |   |
| **61** | 115 | Y |   |
| **62** |     |   |   |
| **63** |     |   |   |
| **64** |     |   |   |
| **65** | 251 | N | product (5 x 13) |
| **66** |     |   |   |
| **67** | 113 | Y |   |
| **68** |     |   |   |
| **69** |     |   |   |
| **70** |     |   |   |
| **71** | 257 | Y |   |
| **72** |     |   |   |
| **73** | 111 | Y |   |
| **74** |     |   |   |
| **75** |     |   |   |
| **76** |     |   |   |
| **77** | 255 | N | product (7 x 11) |
| **78** |     |   |   |
| **79** | 117 | Y |   |
| **80** |     |   |   |
| **81** |     |   |   |
| **82** |     |   |   |
| **83** | 253 | Y |   |
| **84** |     |   |   |
| **85** | 115 | N | product (5 x 17) |
| **86** |     |   |   |
| **87** |     |   |   |
| **88** |     |   |   |
| **89** | 251 | Y |   |
| **90** |     |   |   |
| **91** | 113 | N | product (7 x 13) |
| **92** |     |   |   |
| **93** |     |   |   |
| **94** |     |   |   |
| **95** | 257 | N | product (5 x 19) |
| **96** |     |   |   |
| **97** | 111 | Y |   |
| **98** |     |   |   |
| **99** |     |   |   |
| **100** |     |   |   |
| **101** | 255 | Y |   |
| **102** |     |   |   |
| **103** | 117 | Y |   |
| **104** |     |   |   |
| **105** |     |   |   |
| **106** |     |   |   |
| **107** | 253 | Y |   |
| **108** |     |   |   |
| **109** | 115 | Y |   |
| **110** |     |   |   |
| **111** |     |   |   |
| **112** |     |   |   |
| **113** | 251 | Y |   |
| **114** |     |   |   |
| **115** | 113 | Y |   |
| **116** |     |   |   |
| **117** |     |   |   |
| **118** |     |   |   |
| **119** | 257 | N | product (7 x 17) |
| **120** |     |   |   |
| **121** | 111 | N | square (11²) |
| **122** |     |   |   |
| **123** |     |   |   |
| **124** |     |   |   |
| **125** | 255 | N | cube (5³) |
| **126** |     |   |   |
| **127** | 117 | Y |   |
| **128** |     |   |   |
| **129** |     |   |   |
| **130** |     |   |   |
| **131** | 253 | Y |   |
| **132** |     |   |   |
| **133** | 115 | N | product (7 x 19) |
| **134** |     |   |   |
| **135** |     |   |   |
| **136** |     |   |   |
| **137** | 251 | Y |   |
| **138** |     |   |   |
| **139** | 113 | Y |   |
| **140** |     |   |   |
| **141** |     |   |   |
| **142** |     |   |   |
| **143** | 257 | N | product (11 x 13) |
| **144** |     |   |   |

## Base 24 and the Core Prime Identities

Ideally, we will have a single symbol to refer to each of the eight codes, instead of three symbols linked together in a sequence. We want one digit instead of three to avoid confusion and because we do not want the symbol for a code to be broken apart.

We can have a single symbol for each of the eight codes by using 24 as our number base. When a number base requires symbols beyond the usual set (0 - 9), the additional numbers are represented by something else that is already available to write and type, such as letters. For base 24, the number 10 is represented by A and the sequence continues until 23 which is represented by N. The notation B24 is used to refer to the last digit of a number translated into base 24 and the value can be attached after a colon, such as B24:7 which is notation for a base 24 value of 7.

| Number | B3:6:8 Code | B24 Code |
| ----------- | ----------- | ----------- |
| **0** |     | 0 |
| **1** | 111 | 1 |
| **2** |     | 2 |
| **3** |     | 3 |
| **4** |     | 4 |
| **5** | 255 | 5 |
| **6** |     | 6 |
| **7** | 117 | 7 |
| **8** |     | 8 |
| **9** |     | 9 |
| **10** |     | A |
| **11** | 253 | B |
| **12** |     | C |
| **13** | 115 | D |
| **14** |     | E |
| **15** |     | F |
| **16** |     | G |
| **17** | 251 | H |
| **18** |     | I |
| **19** | 113 | J |
| **20** |     | K |
| **21** |     | L |
| **22** |     | M |
| **23** | 257 | N |
| **24** |     | 0 |

We now have a set of eight core identities which can be used as archetypes (templates of B24 number types) that continue to interact with each other in the same manner all throughout the number line.

- 1
- 5
- 7
- B (aka 11)
- D (aka 13)
- H (aka 17)
- J (aka 19)
- N (aka 23)

## Example Interaction of Core Prime Identities

The tendency of these identities to form products of type B24:1 is a good initial example of how the core eight identities interact with each other. Every product of two of the same type will be a type B24:1, and this includes every even-numbered exponent of any of the types.

If we use 13 (B24:D) and 37 (B24:D) and multiply them together, their product 13 x 37 = 481 (B24:1) is a B24 type 1, as expected.

If we square 5 (B24:5) we get 5² = 25 (B24:1) and if we raise 7 (B24:7) to the fourth we get 7⁴ = 2401 (B24:1), which is also a B24 type 1, as expected.

Because more combinations of these identities make type 1 than anything else, and because combinations cannot be primes, we should see fewer "1 primes" relative to other types as we go further along the number line.

This is, in fact, what we see. 



## Cyclical B24 Number System



## Primes Bracket Multiples of Six


## Efficient Identification of Primes





