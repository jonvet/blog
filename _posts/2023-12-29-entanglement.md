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
Imagine we have a laser that can shoot an individual photon onto some kind of crystal, which produces the entangled state $\Psi^{+}$ above.
And since we are talking about photons specifically, let's use the photon's polarization to describe which state they're in.

In particular, let's say that a vertically polarized photon corresponds to the state $\ket{V}$ and a horizontally polarized photon to state $\ket{H}$. So our entangled state now looks like $\frac{\ket{VH}+\ket{HV}}{\sqrt{2}}$.
Continuing with our experimental setup, imagine we give the first of this pair of entangled qubits to Alice and the second to Bob.

Now instead of referring to the qubits as "first" and "second" we can label them with Alice's and Bob's initials: $\frac{\ket{V_{A}}\ket{H_{B}} + \ket{H_{A}}\ket{V_{B}}}{\sqrt{2}}$ 

Lastly, Alice and Bob are equipped with a measurement device, a linearly polarized lens.
For the sake of simplicity (we are going to relax this assumption later) assume that both Alice and Bob orient their lens at $90^{\circ}$ making them vertically polarized lenses.

# Experiment outcomes
As both photons are in superposition, Alice and Bob are *a priori* equally likely to observe that their lens either blocks the photon or let's it through.
Note that the joint state does not contain $\ket{V_{A}}\ket{V_{B}}$ or $\ket{H_{A}}\ket{H_{B}}$ which means that it's not possible for both of them to see a photon, or for neither of them to see a photon (assuming they keep using their vertical and horizontal lenses). It's certain that one of them will see the photon and the other one doesn't.

Moreover, while either of the 2 outcomes are 50% likely before the experiment, if Alice were to use her lens first and saw a photon, Bob would know with certainty that he wouldn't observe a photon without having to measure it. Likewise, if Alice were to use her lens but didn't see a photon, then Bob would know without measuring that he will definitely see a photon.

The reason this happens is that the act of measuring alters the joint state. Measuring a photon with a vertically polarized lens means applying the bra $\bra{V}$. Since the vertical and horizontal lenses are perpendicular to each other (they are basis states) we know that $\braket{V|V}=1$ and $\braket{V|H}=0$. So if Alice observes the photon, which is in equal superposition of the states $\ket{V}$ and $\ket{H}$, with her vertically polarized lens and sees the photon, we know with certainty that the joint state of the entangled photons is $\ket{V_{A}}\ket{H_{B}}$. That is, her act of measuring collapses the joint state to $\ket{V_{A}}\ket{H_{B}}$.

# What's special about this?
If you wonder why this is exciting, consider a classical variant of this experiment. Instead of 2 quantum objects let's use 2 everyday objects like socks. Imagine that we have a red and a blue sock and put them into separate boxes. We then send Alice and Bob one of the boxes each at random. If Alice opens her box first and observes a red sock, then Bob knows with certainty that his sock will be blue, and vice versa. It is also impossible for both Alice and Bob to get a red sock, or both to get a blue sock. So everything seems exactly the same as in our photon experiment. 

But here is the difference: the socks have a definitive colour at any time during the experiment. This is different from our photons. Until they are measured the photons are in superposition, which means they do not have a definitive polarization. In our experiment, Alice's photon doesn't have a definitive polarization until she measures it with her lens. Only at that point is the polarization of her photon determined. And what's more, also the polarization of Bob's photon is determined, even though it is not measured. The strange this is not only that, but also that this seems to imply that even if the photons were millions of miles apart, measuring Alice's photon would "immediately" determine the state of Bob's photon. but clearly that can't be possible, because nothing can travel faster than the speed of light, including the information of Alice's measurement.

This is the "spooky action at a distance" that Einstein referred to.

One explanation for this strangeness was the existence of some hidden variables, which

