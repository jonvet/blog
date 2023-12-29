---
title: "ENTANGLEMENT"
date: 2023-12-28
---

# Entanglement

Once referred to as "spooky action at a distance" by Einstein, entanglement is one of the most puzzling aspects of quantum mechanics. 
It's implications are counterintuitive to us, because we we are used to interacting with objects on "human scale", or a few orders of magnitude smaller than that. 
Quantum particles on the other hand are many more orders of magnitude smaller. 
Perhaps one of the largest quantum objects created so far is a [sapphire crystal](https://www.scientificamerican.com/article/physicists-create-biggest-ever-schroedingers-cat/) weighing 16 micrograms and consisting of about $10^{17}$ atoms. 
That's truly is small, but quantum particles used in experiments or actual quantum computers, such as ions, electrons or photons, are even smaller. 
When studying quantum mechanics it's a recurring theme that on such small scales, the world just works differently than what we're used to. 
Entanglement is a specific manifestations of this.

In this blog post we're trying to explore what entanglement is on a mathematical level.

# Bell's states

We first consider the simplest example of achieving entanglement: a [Bell state](https://en.wikipedia.org/wiki/Bell_state). 
Specifically, we create the Bell state $\Psi^{+} = \frac{\ket{01}+\ket{10}}{\sqrt{2}}$, which is obtained by 
- starting with a 2 qubit register with one qubit in the $\ket{0}$ and one in the $\ket{1}$ state
- applying the Hadamard gate to the first qubit
- applying the CNOT controlled by the first qubit
<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/The_Hadamard-CNOT_transform_on_the_zero-state.png" />
</p>

Both qubits are in superposition, that is, if we were to measure either one we would find that they are in the $\ket{0}$ and the $\ket{1}$ states with 50% probability each.
Their entanglement means that they are also correlated: if we were to measure the first qubit to be $\ket{1}$ then we also know with certainty that the second qubit is in state $\ket{0}$.

# Making things more concrete
Rather than talking about our qubits as abstract concepts, let's consider the case where we run an experiment using photons. 
Imagine we have a laser can shoot an individual photon onto some kind of crystal, which produces the entangled state $\Psi^{+}$ above.
And since we are talking about photons specifically, let's use the photon's polarization to describe which state they're in.

In particular, let's say that a vertically polarized photon corresponds to the state $\ket{V}$ and a horizontally polarized photon to state $\ket{H}$. So our entangled state now looks like $\frac{\ket{VH}+\ket{HV}}{\sqrt{2}}$.
Continuing with our experimental setup, imagine we give the first of this pair of entangled qubits to Alice and the second to Bob.

Now instead of referring to the qubits as "first" and "second" we can label them with Alice's and Bob's initials: $\frac{\ket{V_{A}}\ket{H_{B}} + \ket{H_{A}}\ket{V_{B}}}{\sqrt{2}}$ 

Lastly, Alice and Bob are equipped with a measurement device, a linearly polarized lens.
For the sake of simplicity (we are going to relax this assumption) assume that Alice orients her lens at $90^{\circ}$ making it a vertically polarized lens, and Bob keeps his as $0^{\circ}$ making it a horizontally polarized lens.

As both photons are in superposition, Alice and Bob are a priori equally likely to observe that their lens either blocks the photon or let's it through.
Specifically the probabilities of each of the 4 outcomes are
$$\text{Alice observes photon, Bob's gets blocked:} \bra{V_{A}}\ket{V_{A}}\bra{V_{B}}\ket{H_{B}} + \ket{H_{A}}\ket{V_{B}}$$
