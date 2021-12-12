# QKE

## Photon as Qubit

For the purpose of this example I will consider photons as qubits, otherwise qubits can also be thought of as electrons spin, quantum dot etc.

Photon has two types of polarizations: **linear** and **elliptical**.
We don’t need to know about elliptical polarization here. Linear polarization has two states: **rectilinear** and **diagonal**.
Again Rectilinear polarization is of two types: **horizontal** and **vertical**. 
And Diagonal polarization is also of two types: **diagonal** and **anti-diagonal**.

It's obvious that we have a two-level system(we would have one-level system if we would only choose between rectilinear and diagonal type, but we can also choose a type of both).
Thus we can decide upon such encoding:

| 	      	 | Rectilinear |
| -------------- | ----------- |
| horizontal |H> | |0>         |
| vertical |V>   | |1>         |


| 	      	   | Diagonal    |
| ---------------- | ----------- |
| diagonal |D>     | |0>         |
| antidiagonal |A> | |1>         |

## Key Exchange

As a convention we will establish a secure channel between Bob and Alice.

1.) Alice randomly selects a string of bits and a string of bases(rectilinear or diagonal) of equal length. Then she transmits a photon for each bit with the corresponding polarization to Bob
2.) Now Bob for each received photon, randomly chooses a basis(rectilinear or diagonal)
3.) Bob and Alice communicate through a public(unsecure) channel and match bases they have choosen. Alice informs Bob of the bases he guessed correctly. Bob and Alice then removes all bits for which Bob guessed basis wrong. 
4.) Now, Alice and Bob have the same bit-string - the KEY.

## Security

Qubit or in our case photon cannot be measured without being perturbated or in other words without changing it's state.
Therefore:
- Bob and Alice share a few bits(about 10% usually) and check if they match. Any dissagrement of compared bits will expose the presence of attacker.
- Eve has no way to know the bases Alice used to encode the bits before Alice reveals her coding bases in the public channel. So, Eve needs to guess the bases to measure the photons. If she measures on the wrong basis, she cannot replicate the states of the intercepted photons before sending it to Bob. 


## Why it this key exchange more secure?

It's properties are based on physics rather then on math. Math can eventually be broken by using really really really strong computers, while physics not (yet).
