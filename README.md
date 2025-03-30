## Exp: Huffman-Shannon_fano
## Name: Akshaya Settu
## Reg No.: 212223060014
### Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### Aim :
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### Tools Required :
Python IDE with
-> numpy library
-> math library

### Program :
``` python
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
### Calculation :

![Screenshot 2025-03-30 143931](https://github.com/user-attachments/assets/098383bb-9640-4c74-8943-37b104b44bf5)

![WhatsApp Image 2025-03-30 at 14 44 53_5001d268](https://github.com/user-attachments/assets/4ff90c0d-3c57-4ba7-9325-010329626721)

![WhatsApp Image 2025-03-30 at 14 44 53_2f39bd44](https://github.com/user-attachments/assets/aaf44d55-f27b-4309-8f0c-23a75157bd7a)

![WhatsApp Image 2025-03-30 at 14 44 54_d4878fbf](https://github.com/user-attachments/assets/08b969e1-2e8c-4a1c-b335-6d540e5f8b0b)

![WhatsApp Image 2025-03-30 at 14 44 54_e93c095c](https://github.com/user-attachments/assets/acb9a81a-293e-428c-a145-ce1d0ed09d83)

### Results :
The obtained result are

Average Codeword Length is : 2.625

Entropy is : 2.625

Efficiency is : 1.0

Redudancy is : 0.0

Variance is : 0.484
