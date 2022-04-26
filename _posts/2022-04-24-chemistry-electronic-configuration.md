---
layout: single
title: Chemistry electronic configuration python script
excerpt: "A script that automates the electronic configuration of the elements."
date: 2022-04-24
classes: wide
header:
  teaser: /assets/images/chemistry/atom.jpg
  teaser_home_page: true
  icon: /assets/images/programmingLanguages/python.png
categories:
  - chemistry
  - python
tags:  
  - automatization
---

## What is the electronic configuration?

### A chemistry electronic configuration is the organization of electrons in the different electron orbitals. Those orbitals are divided in different levels:

![](/assets/images/chemistry/electronic_configuration.png)

### This can be automated easily, so I used Python to make a script which can make this configuration applying the electronic charge.

## Script

### Foremost, I create 2 variables. One that specify the order of the electron and the level, and another that assign the value to the different orbitals.

```
orbitals = ["1s", "2s", "2p", "3s", "3p", "4s", "3d", "4p", "5s", "4d", "5p", "6s", "4f", "5d", "6p", "7s", "5f", "6d", "7p"]
orbitalsValue = {"s": 2, "p": 6, "d": 10, "f": 14}
```

### Then I collect the atomic mass and the charge, later I get the electron number. Then I create the variable where I will add the result.

```
atomicMass = int(input("Insert the atomic mass of the element: "))
electricCharge = int(input("Insert the electric charge that the element have (0 is none): "))
electrons = atomicMass - electricCharge

result = ""
```

### In a for loop, I get the orbital and then check if the electrons given are greater or smaller than the value of the orbital, and then I add the result to the variable result. Finally, when breaking the for loop, I print the result.

```
for i in range(electrons):
    value = orbitalsValue[orbitals[i][1]]

    if electrons == 0:
        break
    elif electrons >= value:
        result += " " + orbitals[i] + str(value)
        electrons -= value
    elif electrons < value:
        result += " " + orbitals[i] + str(electrons)
        break

print(result)
```

### This is the final code.

```
orbitals = ["1s", "2s", "2p", "3s", "3p", "4s", "3d", "4p", "5s", "4d", "5p", "6s", "4f", "5d", "6p", "7s", "5f", "6d", "7p"]
orbitalsValue = {"s": 2, "p": 6, "d": 10, "f": 14}

atomicMass = int(input("Insert the atomic mass of the element: "))
electricCharge = int(input("Insert the electric charge that the element have (0 is none): "))
electrons = atomicMass - electricCharge

result = ""

for i in range(electrons):
    value = orbitalsValue[orbitals[i][1]]

    if electrons == 0:
        break
    elif electrons >= value:
        result += " " + orbitals[i] + str(value)
        electrons -= value
    elif electrons < value:
        result += " " + orbitals[i] + str(electrons)
        break

print(result)
```

### Example:
```
Insert the atomic mass of the element: 20
Insert the electric charge that the element have (0 is none): -3
1s2 2s2 2p6 3s2 3p6 4s2 3d3
```
