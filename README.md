# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM:
```
To find the efficiency of huffmann and shannon fano coding.
```
# SOFTWARE REQUIRED
```
colab software
```
# ALGORITHMS
```
Step 1: Start the program.
Step 2: Initialize variables:
    L = 0 (for average codeword length)
    hs = 0 (for entropy)
    Empty lists: p[] for probabilities and lk[] for codeword lengths
Step 3: Input the number of samples n.
Step 4: For each sample from 1 to n:
    → Input the probability pr
    → Append pr to list p[]
Step 5: For each sample from 1 to n:
    → Input the codeword length l
    → Append l to list lk[]
Step 6: Calculate Average Codeword Length L:
    → For each k from 0 to n-1:
        → L += p[k] * lk[k]
Step 7: Calculate Entropy hs:
    → For each k from 0 to n-1:
        → hs += p[k] * log2(1 / p[k])
    → Round hs to 3 decimal places
Step 8: Calculate Efficiency eff:
    → eff = hs / L
    → Round eff to 3 decimal places
Step 9: Calculate Redundancy red:
    → red = 1 - eff
    → Round red to 3 decimal places
Step 10: Calculate Variance var:
    → Initialize var = 0
    → For each k from 0 to n-1:
        → var += p[k] * (lk[k] - L)^2
    → Round var to 3 decimal places
Step 11: Display the results
    → Print Average Codeword Length L
    → Print Entropy hs
    → Print Efficiency eff
    → Print Redundancy red
    → Print Variance var
Step 12: End the program.
```
# PROGRAM
```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
# OUTPUT

```
Enter the number of Samples : 5
Enter the probability of sample values 1: 0.5
Enter the probability of sample values 2: 0.4
Enter the probability of sample values 3: 0.3
Enter the probability of sample values 4: 0.2
Enter the probability of sample values 5: 0.1
Enter the length of the sample values 1: 1
Enter the length of the sample values 2: 2
Enter the length of the sample values 3: 3
Enter the length of the sample values 4: 4
Enter the length of the sample values 5: 5
Average Codeword Length is : 3.5
Entropy is : 2.346
Efficiency is : 0.67
Redudancy is : 0.33
Variance is : 4.375
```
# RESULT
```
Thus the efficiency of huffman and shannon fano-coding was obtained.
```



