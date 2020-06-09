# floating-point-representation
This repository contains a Java program that demonstrates one of the way to represent floating-point numbers.

# introduction
Let's first understand how the ListRealNumbers program reprents the floating-point numbers.
Let's say we have a total of n-bits out of which e-bits represents the exponent-bits e.g. if total number of bits are 8 and number of exponent bits are 3 then we represent S E E E M M M M as 8-bit floating-point number where S corresponds to sign-bit, E E E corrsponsed to exponent bits and M M M M corresponds to mantissa bits.

# bit-pattern
1. a pattern where E = 11..11 i.e. all bits are one and M = 00.00 i.e. all bits are zero then it represents infinity (-infinity or +infinity depending on whether S bit is set or not)
2. a pattern where E = 11..11 i.e. all bits are one and at least one of the M-bit is set then it represents NaN i.e. Not-a-Number
3. a pattern where E = 00..00 i.e. all bits are zero and at least one of the M-bit is set then it represents a denormal-number.
4. a pattern where E = 00..00 i.e. all bits are zero and M = 00..00 i.e. all bits are zero then it represents zero (-0 or +0) depending on sign-bit. Yes, we have two representation of zero because we are not using two's complement here!
5. other pattern represents normal floating-point numbers and are computed as shown: Let's consider the following bit-pattern where at least one of the E-bit is set but not all S E1 E2 E3 M1 M2 M3 M4
We compute (-1^S)x(1 + 2^-M1 + 2^-M2 + 2^-M3 + 2^-M4)x(2^biasedExponent)
For more-information you can look at the source code(ListRealNumbers.zip)

# execution
1. chmod +x ListRealNumbers.jar : This command will give execution permission to ListRealNumbers.jar file
2. java -jar ListRealNumebrs.jar #totalBits #exponentBits reportFileName 
e.g. java -jar ListRealNumbers.jar 8 3 eight-three.txt

# disclaimer
ListRealNumbers program was written for educational purposes and the author reserves the right not be responsible for the correctness, completeness or quality of the information provided. Liability claims regarding damage caused by the use of the information provided, included any kind of information which is incomplete or incorrect, will therefore be rejected. This program might be extended, changed or partly or completely deleted by the author without any separate announcement.

# open for suggestions
If you find anything incorrect or incomplete please contact shubhampanchal9773@gmail.com


