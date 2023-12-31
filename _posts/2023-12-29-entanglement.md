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
Specifically, we create the Bell state $\Psi^{-} = \frac{\ket{01}-\ket{10}}{\sqrt{2}}$, which is obtained by 
- starting with a 2 qubit register with both qubits in the $\ket{1}$ state
- applying the Hadamard gate to the first qubit
- applying the CNOT controlled by the first qubit, acting on the second
<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/f/fc/The_Hadamard-CNOT_transform_on_the_zero-state.png" />
</p>

Both qubits are in superposition, that is, if we were to measure either one we would find that they are in the $\ket{0}$ and the $\ket{1}$ states with 50% probability each.
Their entanglement means that they are also correlated: if we were to measure the first qubit to be $\ket{1}$ then we also know with certainty that the second qubit is in state $\ket{0}$.

# Making things more concrete
Rather than talking about our qubits as abstract concepts, let's consider the case where we run an experiment using photons. 
Imagine we have a laser that can shoot an individual photon onto some kind of crystal, which produces the entangled state $\Psi^{-}$ above.
And since we are talking about photons specifically, let's use the photon's polarization (vertical or horizontal) to describe which state they're in.

In particular, let's say that a vertically polarized photon corresponds to the state $\ket{V}$ and a horizontally polarized photon to state $\ket{H}$. So our entangled state now looks like $\frac{\ket{VH}-\ket{HV}}{\sqrt{2}}$.
Continuing with our experimental setup, imagine we give the first of this pair of entangled qubits to Alice and the second to Bob.

Now instead of referring to the qubits as "first" and "second" we can label them with Alice's and Bob's initials: $\frac{\ket{V_{A}}\ket{H_{B}} - \ket{H_{A}}\ket{V_{B}}}{\sqrt{2}}$ 

Lastly, Alice and Bob are equipped with a measurement device, a linearly polarized lens.
For the sake of simplicity (we are going to relax this assumption later) assume that both Alice and Bob orient their lens at $90^{\circ}$ making them vertically polarized lenses.

# Experiment outcomes
As both photons are in superposition, Alice and Bob are *a priori* equally likely to observe that their lens either blocks the photon or let's it through.
Note that the joint state does not contain $\ket{V_{A}}\ket{V_{B}}$ or $\ket{H_{A}}\ket{H_{B}}$ which means that it's not possible for both of them to see a photon, or for neither of them to see a photon (assuming they keep using their vertically polarized lenses). It's certain that one of them will see the photon and the other one doesn't.

Moreover, while either of the 2 outcomes are 50% likely before the experiment, if Alice were to use her lens first and saw a photon, Bob would know with certainty that he wouldn't observe a photon without having to measure it. Likewise, if Alice were to use her lens but didn't see a photon, then Bob would know without measuring that he will definitely see a photon.

The reason this happens is that the act of measuring alters the joint state. Mathematically, measuring a vertically polarized photon, which is described by the ket $\ket{V}$, with a vertically polarized lens means applying the bra $\bra{V}$ to it. Since the vertical and horizontal lenses are perpendicular to each other (they are basis states) we know that $\braket{V|V}=1$ and $\braket{V|H}=0$. So if Alice observes the photon, which is in equal superposition of the states $\ket{V}$ and $\ket{H}$, with her vertically polarized lens and sees the photon, we know with certainty that the joint state of the entangled photons is $\ket{V_{A}}\ket{H_{B}}$. That is, her act of measuring collapses the joint state to $\ket{V_{A}}\ket{H_{B}}$.

# What's special about this?
If you wonder why this is exciting, consider a classical variant of this experiment. Instead of 2 quantum objects let's use 2 everyday objects like socks. Imagine that we have a red and a blue sock and put them into separate boxes. We then send Alice and Bob one of the boxes each at random. If Alice opens her box first and observes a red sock, then Bob knows with certainty that his sock will be blue, and vice versa. It is also impossible for both Alice and Bob to get a red sock, or both to get a blue sock. So everything seems exactly the same as in our photon experiment. 

But here is the difference: the socks have a definitive colour at any time during the experiment. This is different from our photons. Until they are measured the photons are in superposition, which means they do not have a definitive polarization. In our experiment, Alice's photon doesn't have a definitive polarization until she measures it with her lens. Only at that point is the polarization of her photon determined. And what's more, also the polarization of Bob's photon is determined, even though it is not measured. The strange thing is not only that, but also that this seems to imply that even if the photons were millions of miles apart, measuring Alice's photon would "immediately" determine the state of Bob's photon. but clearly that can't be possible, because nothing can travel faster than the speed of light, including the information of Alice's measurement.

This is the "spooky action at a distance" that Einstein referred to.

# Hidden variables and Bell's Inequality
To Einstein the conundrum of entanglement only seemed possible if the joint state of the two photons somehow got determined locally before they were separated and sent to Alice and Bob. So the information that Alice's photon will be measured in the $\ket{V}$ state and Bob's in the $\ket{H}$ state would have to be stored in a hidden, unobservable variable.

There is a great [blog post](https://www.sciencenews.org/blog/context/entanglement-spooky-not-action-distance) about the disagreement of Einstein and Bohr on this topic. For the remainder of this blog post we'll talk about Bell's Inequality and how it disproves the notion of hidden variables. Entanglement appears to be spooky after all!

To start off, recall that so far we've equipped Alice and Bob with vertically polarized lenses. Given the fact that we put our photons in the joint state $\Psi^{-}$, in which both photons are in equal superposition of the $\ket{V}$ and $\ket{H}$ states, Alice and Bob always obtain one of the 2 results: either Alice sees a photon and Bob doesn't, or Alice doesn't see a photon and Bob does. In other words, their measurements __always disagree__.

However things change if we allow Alice and Bob to slightly rotate their lenses to obtain a diagonal polarization of somewhere between $0^{\circ}$ and $90^{\circ}$. In this case, even if Alice measures a vertically polarized photon, which means that Bob's photon in horizontally polarized, there is still a chance that he also observes a photon. So if Alice and Bob orient their lenses differently it's possible for their measurements to __agree or disagree__.

The proof that hidden variables cannot explain the relationship between entangled quantum particles works by contradiction. First, we assume that hidden variables do explain entanglement and derive an inequality that has to hold if the hypothesis of hidden variables was true. This inequality was originally derived by John Bell in 1964, and it puts a limit on how often Alice and Bob's measurements would match. Then we run actual quantum experiments to show that the inequality doesn't always hold. Alice and Bob's measurements can actually match more often. This disproves that hidden variables are the driving force behind the "spooky action at a distance" and provides evidence for the standard quantum view that quantum particles have properties that are only determined when measured.

So let's start with the assumption that hidden variables are a valid explanation. We change the experimental setup and allow Alice and Bob to randomly rotate their lens to $0^{\circ}$, $30^{\circ}$ and $60^{\circ}$ instead of just using a vertically polarized lens. Remember we said that before we send the photons to Alice and Bob, their joint state has to be determined locally and stored in some kind of hidden variable. The hidden state of the photon is then a rule that determines whether it will pass through Alice and Bob's lenses at each of the 3 orientations. And in order to be in line with the joint Bell state, it has to be the case that when Alice and Bob end up choosing the same orientation, their measurement results will disagree, e.g. Alice sees a photon and Bob doesn't.

There are 8 different hidden states the photons can take:

