# helium_project
Python animation of Helium in 2 excited states by computing wavefunctions in time

Simulations of the Helium Atoms in Two Excited States

Tung D. Nguyen and Nhan D. Nguyen 

Instructor: James Brown, Ph.D.

Wabash College, Indiana

February 2019

1. Introduction
- Our project’s theme was motivated from combining the foundation of quaNtum mechanics and quantum chemistry. We aimed to utilize both of the branches of science to study simulations of basic atoms in the periodic table. To study the atoms’ motions with a high uncertainty of positions, we utilized the Python coding language (version 3), due to its efficacy in dealing with motions simulation. In Python, there is a variety of packages involving molecular simulations of those atoms. Most of the time, the simulations from these packages lack several aspects of quantum mechanics of electrons’ motions. The lacking of details relevant to constructions of quantum mechanics motivated us to simulate basic atoms to a more understandable degree for undergraduate students, given their basic Python knowledge. Combining with our interest in quantum mechanics, we aimed to simulate Helium by using the well-known Schrodinger equation (2).

- In this project, we mainly run on Python version 3.6.8 to simulate the most basic atom after Hydro: the Helium atom. Our main concentration was to simulate the motions of two electrons revolving around Helium’s nucleus by using the wavefunction’s formulas of linear combinations of two electrons and simulating their positions by using the Monte Carlo method.
2. Procedures

a. Theoretical model:
- From [1], the theoretical model includes the Schrodinger equation of the Helium atoms, with the potentials between the electrons and between the electron and the nucleus. The potential functions are constructed from the radius distance of each electron from the nucleus.
     
<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/iZw4aIH.png" alt="Commercial Photography"></a>

for

<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/QJoSG0X.png" alt="Commercial Photography"></a> (1)

,where <a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/dc5dorb.png" alt="Commercial Photography"></a>, and <a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/NLRwNI8.png" alt="Commercial Photography"></a>
the potential functions between the first electron and the nucleus, the second electron and the nucleus, and two electrons. This model can fully describe the probabilistic values of the positions; however, the calculations are very complicated, as <a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/VBlVN4I.png" alt="Commercial Photography"></a> makes the wavefunctions of two electrons inseparable. To solve this problem, we assume that the potential between two electrons is negligible and separate the initial equation into two equations, for each representing the electron interaction with the nucleus, as follows:

<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/tvfA3Tg.png" alt="Commercial Photography"></a>

for

<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/jNeGsru.png" alt="Commercial Photography"></a>

- Solving these equations, we obtain the following formulas of the wavefunctions, expressing in spherical coordinates:
<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/mToDNuq.png" alt="Commercial Photography"></a>

,where we have principal quantum number n_i, angular quantum number l_i, and the azimuthal quantum number m_i. From here, the energy value is calculated by E = E_1 + E_2. All of these functions can be obtained from the libraries of Python and enable us to derive the desired plots for wavefunctions and the energy values.

- In this study, the two excited states 2p and 3p of helium were examined. It is known that helium has the orbital model of 1s2. According to the orbital dia- grams, the arrangement of orbital’s energy level is as follows: <a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/KvbpErn.png" alt="Commercial Photography"></a>. Choosing 2p and 3p as excited states is reasonable because they both have higher energy levels than the ground state (s) and have a similar orbital shape (a 2D dumbbells, as expected). The plotting of p orbital state also took median memory to compute, which is sufficient for our short-term project.

b. Computational method:
     
- The simulation was run on Python version 3.6.8. There are several libraries used for the computation. Numpy was used for handling arrays and auxiliary mathematical operations; Random package to generate random distribution in Monte Carlo for our mathematical model; Pylab and Matplotlib.pyplot for plotting the wavefunctions and the animations of 2 electrons in 2 excited states (2p and 3p), Scipy to determine the spherical harmonics function for positioning electrons on a sphere; Seaborn to sketch density maps of electron distributions; Simpy, the most important library, to derive the radial wavefunctions with a given quantum numbers, n, l, and m. Several quantum constants were given Bohr radius, atomic number of Helium (Z = 2), sampling size N for number of points in Monte Carlo method. Spherical functions were taken from Scipi.spe, which were multiplied by radial functions to obtain the full wave- functions. While both the Helium ground state’s electrons are at 2s state, the computational model aimed to simulate Helium atoms to achieve two very excited states, 2p and 3p, which are theoretically determined. Wavefunctions were refined by getting rid of low density areas of electron clouds, defined as average values of a wavefunction (avg value). Animation was applied as updating scattered plots by each plotting points.
     
- In our construction, we first obtained all possible values into two arrays of the coordinates for the electrons with the corresponding density. The overall wavefunction is calculated by multiplying the wavefunctions of electrons with the same index, then we created an array of the overal wavefunction. To map the positions efficiently, we eliminated all regions with low densities, due to the circular density of all possible density regions, to map where the electrons appear occasionally.

3. Results:

<a href="http://www.freeimagehosting.net/commercial-photography/"><img src="https://i.imgur.com/FCpGVWN.png" alt="Commercial Photography"></a>

Figure 1: The motion of Helium electrons with states (n = 2, l = 1) and (n = 3, l = 1) within the density areas

- We have been able to map the position functions of both electrons in a Helium atom. The red and blue density area correspond to the first electron(n=2, l=1) and second electron(n=3, l=1) in the helium atom. In Figure 1, the density of each region change from light to strong color, showing how electrons prefer to appear in the middle region of the dumbell orbitals. This construction of wavefunction doesn’t mean to include a specific quantum number m, as we map the superposition of wavefunctions of every possible state m in the electron-nucleus wavefunction. The density plots are constructed by using the Seaborn library, and the electron points are constructed by Matplotlib.

4. Discussion and conclusion

- Overall, we interpreted the atomic simulation on Python under the aspects of quantum mechanics. The combination of multiple libraries, such as Numpy and Scipy, encouraged us to do the simulation from cleaner construction of wavefunctions’ formulas. However, the command ”append” from our simulation took a lot of computer’s memory, which took our running time from two to three minutes in total. For future references, we hope to develop a much more memory-saving method of ”append,” such as by combining the append and elimination process of desired values of the wavefunctions simultaneously.

- We also want to include the energy values for the basic Helium atom. How- ever, we have checked with articles [2] and [3] and found inconsistent results of energy values, especially on ground state value. We hope to develop this method in the future.

5. References

[1] David J. Griffith, Introduction to Quantum Mechanics. Reed College. Pren- tice Hall. Upper Saddle River, New Jersey. 2002.

[2] Mohammad Mostafanejad, Direct Methods For Solving the Schr ̈odinger Equation, Open Research. Australian National University. November 2016.

[3] D.T. Aznabaev, Nonrelativistic energy levels of helium atom. Atomic Physics. Phys. Rev. A, vol. 98, 012510. October 2018.
