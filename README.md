# QKE

## Qubit as a photon

For the purpose of this example I will consider qubits as photons, otherwise qubits can also be thought of as electrons spin, quantum dot etc.

Before understanding how photon relates to qubit we need to understand the concept of polarization.
Photon (waves) can be polarized in three different ways: **linear**, **circular** and **elliptical**:
- **Linear polarization** is a type of light polarization where the waveform of light is limited to a single plane(Often seen as a waveform we see if we filter circular wave for a particular angle)

- **Circular Polarization** is a type of light polarization when there are two waves that are perpendicular to each other (e.g. Electromagnetic wave) while also having the same amplitude and phase shift

- **Elliptical Polarization** is a type of light polarization similar to Circular polarization, while the two waves have different amplitudes and different phase shift

The last two polarization are mentioned to avoid any confusion later on.

For the case of QKE we will consider linear polarization. Its "sub-types" are **rectilinear** or **diagonal** polarization.
Rectilinear polarization and its correspoding qubit state is chosen as: **horizontal |0>** and **vertical |1>**.

Diagonal polarization and its corresponding qubit state is chosen as: **diagonal |0>** and **anti-diagonal |1>**.

## Key Exchange

The purpose of the exchange is to establish a secure channel between Bob and Alice.

1.) Alice randomly selects a string of bits and a string of bases(rectilinear or diagonal) of equal length. Then she transmits a photon for each bit with the corresponding polarization to Bob
2.) Now Bob for each received photon, randomly chooses a basis(rectilinear or diagonal)
3.) Bob and Alice communicate through a public(unsecure) channel and match bases they have choosen. Alice informs Bob of the bases he guessed correctly. Bob and Alice then removes all bits for which Bob guessed basis wrong. 
4.) Now, Alice and Bob have the same bit-string - the KEY.

## Security

Qubit or in our case photon cannot be measured without being perturbated or in other words without changing it's state.
TODO: Add qubit measuring
Therefore:
- Bob and Alice share a few bits(about 10% usually) and check if they match. Any dissagrement of compared bits will expose the presence of attacker.
- Eve has no way to know the bases Alice used to encode the bits before Alice reveals her coding bases in the public channel. So, Eve needs to guess the bases to measure the photons. If she measures on the wrong basis, she cannot replicate the states of the intercepted photons before sending it to Bob. 


## Why it this key exchange more secure?

It's properties are based on physics rather then on math. Math can eventually be broken by using really really really strong computers, while physics not (yet).
