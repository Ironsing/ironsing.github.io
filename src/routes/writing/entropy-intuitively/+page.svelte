<script>
	import AccentRule from '$lib/AccentRule.svelte';
	import Math from '$lib/Math.svelte';
	import StyledLink from '$lib/StyledLink.svelte';

	const entropyIntegral = String.raw`\Delta S = \int_{i}^{f} \frac{\delta Q_{\mathrm{rev}}}{T}`;

	// LaTeX needing real backslashes; `String.raw` keeps them out of JS escapes.
	const dqOverT = String.raw`\frac{dQ}{T}`;
	const qOverT1 = String.raw`\frac{Q}{T_1}`;
	const qOverT2 = String.raw`\frac{Q}{T_2}`;
	const t1gtT2 = String.raw`T_1 > T_2`;
	const qOverT1ltqOverT2 = String.raw`\frac{Q}{T_1} < \frac{Q}{T_2}`;
	const kelvin = String.raw`\mathrm{K}`;
	const temp200K = String.raw`200\,\mathrm{K}`;
	const oneOverT2gtOneOverT1 = String.raw`\frac{1}{T_2} > \frac{1}{T_1}`;
	const dQOverT = String.raw`\frac{dQ}{T}`;
	const dSsysEq = String.raw`dS_{\text{sys}} = S_{\text{transfer}} + S_{\text{gen}} \tag{1}`;
	const SuniverseAligned = String.raw`\begin{aligned}
S_{\text{universe}} &= S_{\text{sys}} + S_{\text{surr}} \\
&= (S_{\text{transfer}} + S_{\text{gen}}) - S_{\text{transfer}} \\
&= S_{\text{gen}}
\end{aligned} \tag{3}`;
	const dSsurrEq = String.raw`dS_{\text{surr}} = -S_{\text{transfer}} \tag{2}`;
	const SgenReversible = String.raw`S_{\text{gen}} = 0 \quad \text{for reversibles}, \qquad S_{\text{gen}} > 0 \quad \text{for irreversibles} \tag{4}`;
	const Sgen = String.raw`S_{\text{gen}}`;
	const dSdiff = String.raw`dS`;
	const ltZero = String.raw`< 0`;
	const dSsysZeroInline = String.raw`dS_{\text{sys}} = 0`;
	const StransferLteZeroInline = String.raw`S_{\text{transfer}} \leq 0`;
	const eqZero = String.raw`= 0`;
	const dSuniverseGteZero = String.raw`dS_{\text{universe}} \geq 0 \tag{5}`;
	const dSsysZero = String.raw`dS_{\text{sys}} = 0 \tag{6}`;
	const StransferLteZero = String.raw`S_{\text{transfer}} \leq 0 \tag{7}`;
	const StransferEqNegSgen = String.raw`S_{\text{transfer}} = -S_{\text{gen}}`;
	const SgenGteZero = String.raw`S_{\text{gen}} \geq 0`;
</script>

<div
	class="flex min-h-full w-full max-w-180 shrink-0 flex-col gap-4 p-10 text-left leading-7 text-normal lg:p-20"
>
	<StyledLink href="/writing" class="text-sm">← writing</StyledLink>
	<div class="text-2xl text-emphasis">Entropy, intuitively</div>
	<div class="text-muted">26<sup>th</sup> September, 2026</div>
	<AccentRule width="w-3xs lg:w-xl" />
	<div class="flex flex-col gap-6">
		<p>Where to begin? With Boltzmann.</p>
		<p>
			We can model the world at two levels: macro and micro. A microscopic model-a microstate-will
			contain the position, momentum, charge, etc, of every constituent particle. A macroscopic
			model-a macrostate-will just tell you the pressure and volume of the whole. Simple example:
			roll <Math tex="N" display={false} /> dice. A microstate could be the number on each die, and you
			could define the sum as a macrostate.
		</p>
		<p>
			Notice that macroscopic models are <em>abstractions</em>. Reality is actually a soup of
			fundamental particles and fields, but we can still model it extremely well using macro
			aggregates. Macrostates, being abstractions, can have *multiple* microstates corresponding to
			them. There are many ways to roll <Math tex="N" display={false} /> dice to get a sum of
			<Math tex="3N" display={false} />. Similarly, there are a lot of ways to arrange gas particles
			to have some total energy <Math tex="U" display={false} />, but only <em>one</em>
			such that each particle has a specified momentum, position, etc.
		</p>
		<p>
			Some macrostates clearly have more microstates corresponding to them than others. With the
			dice, there's only one roll each for <Math tex="N" display={false} /> or
			<Math tex="6N" display={false} />, and-again-multiple for a sum of
			<Math tex="3N" display={false} />.
		</p>
		<p>
			What affects how many compatible microstates? The conventional explanation is that more
			disordered macrostate means more compatible microstates, but I prefer the term <em
				>constrained</em
			>. The more you constrain the macroscopic value and the more specific you are about it, the
			less internal arrangements produce that value. If you're perfectly specific, your "macrostate"
			just becomes a microstate.
		</p>
		<p>Can we quantify this constrained-ness? Boltzmann did, figuring out that</p>
		<Math tex="S = k_B \ln \Omega" class="text-emphasis" />
		<p>
			where <Math tex="\Omega" display={false} /> is the number of microstates producing a given macrostate,
			<Math tex="k_B" display={false} /> is just a constant, and <Math tex="S" display={false} />
			is entropy, which actually measures how <em>unconstrained</em> the underlying macrostate is. High
			entropy means a macrostate that specifies very little about the underlying microtates, thus having
			many compatible microstates.
		</p>
		<p>
			Why does this mean the entropy of the universe must increase (the second law of
			thermodynamics)? Imagine a universe containing just some gas. No energy flows into or out of
			the gas besides what it started with. We intuitively understand the gas is decidedly <em
				>not</em
			> static internally: its particles are constantly moving and colliding. Clearly it has a different
			microstate at each moment, and it's moving between microstates without energy input. Therefore,
			to not violate energy conservation, each microstate it moves between must have the same total energy.
			Let's also assume that they're all equally likely.
		</p>
		<p>
			The second law of thermodynamics now falls out. Individual microstates are all equally likely,
			but high-entropy macrostates such as "the gas is in thermal equilibrium everywhere" have
			orders upon orders of magnitudes more corresponding microstates than low-entropy macrostates
			like "there is a <Math tex={temp200K} display={false} /> temperature difference between the two
			half-volumes." As the gas wanders evenly through all possible microstates, its trajectory on the
			<em>macro</em>
			level is overwhelmingly likely to be towards higher-entropy macrostates, because they have
			<em>vastly</em>
			many more microstates.
		</p>
		<p>
			Notice that this makes the second law a statement of vast probability, not about something
			fundamentally baked into the structure of reality. It's <em>not</em> impossible for heat to
			flow from cold to hot; for paint in water to spontaneously concentrate back into the dot it
			was initially. It <em>is</em> impossible (given what we currently know) for matter to exceed the
			speed of light. It's just that you'd have to wait much, much longer than the age of the universe
			to watch entropy spontaneously decrease. Unlikely is an understatement, but unlikely isn't impossible.
		</p>
		<p>
			Going back to the gas universe, notice that a low-entropy state such as an internal
			temperature gradient has the same total energy as a high-entropy state, but the former is much
			more useful if we want to extract work out of the gas. Why, if the energy is all still there?
			It's because useful work follows this pattern of two things at different "potential"-
			gravitational, electrical, thermal-which causes a flow between them, and then placing
			something in the path of the flow. Only the lower-entropy state has that gradient. For useful
			work we almost always care about a difference rather than the absolute value.
		</p>
		<p>
			Now notice that the state of having a potential difference is inherently more constrained and
			thus lower-entropy than a state that doesn't have that requirement, so we arrive at the
			unfortunate result that these gradients we care about are overwhelmingly likely to be erased
			even if the energy is all still there, because they're low-entropy. Keeping total energy
			constant, an increase in entropy means a decrease in free energy, the energy available to do
			useful work. Therefore, because the entropy of the universe increases, its free energy
			decreases. Heat death simply means zero free energy, or maximum entropy.
		</p>
		<p>
			I've been talking about entropy from the statistical mechanics angle so far. Now I'm going to
			do so from the thermodynamics angle. Entropy change is defined as
		</p>
		<Math tex={entropyIntegral} class="text-emphasis" />
		<p>
			along a reversible path between <Math tex="i" display={false} /> and
			<Math tex="f" display={false} />. There's no derivation for <Math
				tex={dqOverT}
				display={false}
			/>
			equaling entropy; that's just how Rudolf Clausius defined it. He also proved it's a state function,
			and Boltzmann later showed it equals the statistical-mechanics interpretation above.
		</p>
		<p>
			Consider a fast transfer of <Math tex="Q" display={false} /> joules of heat from a reservoir fixed
			at <Math tex="T_1" display={false} />
			<Math tex={kelvin} display={false} /> to a reservoir fixed at <Math
				tex="T_2"
				display={false}
			/>
			<Math tex={kelvin} display={false} />,
			<Math tex={t1gtT2} display={false} />. <Math tex="T_1" display={false} /> loses
			<Math tex={qOverT1} display={false} /> entropy, <Math tex="T_2" display={false} /> gains
			<Math tex={qOverT2} display={false} /> entropy, but if <Math tex={t1gtT2} display={false} />
			then <Math tex={qOverT1ltqOverT2} display={false} />.
			<em>Simply transferring heat across a finite temperature difference generates entropy.</em>
			Like me, you might initially think that slowing this transfer down infinitely makes it reversible,
			but it doesn't. That makes the heat transferred at each moment an infinitestimal, <Math
				tex="dQ"
				display={false}
			/>. But it does nothing for the temperature difference;
			<Math tex={oneOverT2gtOneOverT1} display={false} /> still holds. To make temperature an infinitesimal
			as well, we'd have to change the process itself by adding infinitely many intermediary bodies, each
			differing by <Math tex="dT" display={false} />.
		</p>
		<p>
			Also, notice that adding the same energy via heat to a hot body increases entropy less than
			doing so with a cold body because the hot body's microstates are already so unconstrained that
			more freedom doesn't change much.
		</p>
		<p>
			To go further we need processes. Thermodynamic systems have state: a complete description of
			them at some moment in time. For a gas, state is
			<Math tex="(P, V)" display={false} />. Now imagine each point in 2D space
			<Math tex="(x, y)" display={false} /> encodes a state using the values of its coordinates. We've
			mapped all possible states to a point on the plane. A process is any curve drawn on the plane, including
			loops.
		</p>
		<p>
			We also distinguish between irreversible and reversible processes. There are a lot of ways
			I've heard them described: reversibles happen infinitely slowly and with infinitesimal
			temperature changes; everything real is irreversible, etc. I think the simplest definition is
			that reversible processes <em>never</em>
			change the entropy of their universe, and irreversible processes <em>always</em> increase it, both
			regardless of cyclicity.
		</p>
		<p>
			And we want to separate a few things. Now that we can quantify entropy using thermodynamic
			quantities, we can talk about the entropy change in the system, just the entropy transferred
			across the system-surroundings boundary, entropy generated in the system but not transferred,
			or change in the universe as a whole (system + surroundings). Spend a moment on that.
		</p>
		<p>Now we're ready to intuit the tangle of inequalities thermodynamics classes teach.</p>
		<p>
			For any process:
			<Math tex={dSsysEq} class="text-emphasis" />
			Just entropy accounting. Also, assuming heat transfer across the interface is reversible:
			<Math tex={dSsurrEq} class="text-emphasis" />
			<Math tex={Sgen} display={false} /> doesn't matter to the surroundings because it never leaves the
			system. Therefore:
			<Math tex={SuniverseAligned} class="text-emphasis" />
		</p>
		<div>
			By definition:
			<Math tex={SgenReversible} class="text-emphasis" />
			Therefore:
			<Math tex={dSuniverseGteZero} class="text-emphasis" />
			For all cyclics, reversible or irreversible:
			<Math tex={dSsysZero} class="text-emphasis" />
			This is because entropy is a state function; <Math tex={dSdiff} display={false} />
			between two states depends only on the difference between them, not on the path used to travel between.
			Clearly the difference between identical states is zero. You might think this contradicts what I
			said about irreversibles earlier, but it doesn't: they do always increase the entropy of their universe,
			but here we're only concerned about the
			<em>system</em>. Again for all cyclics:
			<Math tex={StransferLteZero} class="text-emphasis" />
			Look back at (6). <Math tex={dSsysZeroInline} display={false} /> because of cyclicity, so
			<Math tex={StransferEqNegSgen} display={false} />. <Math tex={SgenGteZero} display={false} />,
			from (4), therefore <Math tex={StransferLteZeroInline} display={false} />. Intuitively: to
			stay cyclic, you have to transfer out as much entropy as you generate. Reversibles generate no
			entropy, so <Math tex={eqZero} display={false} />, and irreversibles do, so they have to
			transfer entropy out, meaning <Math tex={ltZero} display={false} />.
		</div>
		<p>
			And that's entropy. I prefer the statistical mechanics definition. We lifeforms are absurdly
			low-entropy creatures compared to how our constituent atoms would evolve if left alone. If you
			take all my oxygen, hydrogen, carbon, and nitrogen atoms at face value, there are vastly more
			ways to arrange them into not-me than me. Boltzmann's formula captures that in
			<Math tex="\Omega" display={false} />, but I don't currently understand how the
			<Math tex={dQOverT} display={false} /> definition also does, given that they're the same quantity.
			If you do get it, please shoot me an <StyledLink href="mailto:ironsing@proton.me"
				>email</StyledLink
			>. I'm going to close off with an excellent quote I ran into while studying: civilization
			doesn't consume energy; energy is conserved. It consumes low entropy.
		</p>
	</div>
</div>
