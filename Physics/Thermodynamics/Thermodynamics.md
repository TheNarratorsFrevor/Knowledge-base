
Notes:
- When a thermodynamic system does work, it loses heat,
- When work is done on a thermodynamic system, it gains heat,
- So heat is converted to work and work is converted to heat.
## What is a Perpetual Motion machine?

It is a system that can have motion infinitely, which is impossible due to the first law of thermodynamics.

## First law of Thermodynamics

The idea that the change in internal energy is equal to the change in work plus heat, is the fundamental idea of the first law of thermodynamics.

$$\Delta U = Q - W$$
- If heat is transferred into the system, Q > 0
- If heat is transferred out of the system, Q < 0
--- 
- If work is done by the system, W > 0
- If work is done to the system, W < 0 

There are four basic types of processes where the thermodynamic properties of a system (Usually an ideal gas in some kind of container) can change according to the first law, In each case, one of the properties of the system remains constant while the other three may change, here are the properties of a thermodynamic system:

- Volume
- Pressure
- Temperature 
- Heat

#### Iso-volumetric processes

Where the volume of system is held constant, usually because the gas is in a rigid container while heat is being added or removed.
No matter how much heat you add, the gas does not do any work and it just causes an increase in the internal energy. Kinda boring actually.

### Iso-baric processes 

Here, the volume of the container is allowed to change, usually because the gas can move a piston or a lid of some sort.
As you add heat, the volume and the temperature of the system increase and as you remove heat, the volume and the temperature of the system decrease, which essentially means an isobaric process can actually achieve work.
Here's why:
We know that $W = Fd$, in this case the distance that the piston moves is annotated as d.
We have also said that pressure is $P = \frac{F}{A}$, which means that $F = PA$, so we can rewrite our work equation to resemble this: $W = PAd$. and also, we can reason that the area of the piston times the distance it moves is equal to the change in it's volume: $\Delta V = A \Delta d$, so $W = P \Delta V$, pretty cool right?
So when we add heat, volume goes up and the system does work, if we add pressure, volume goes down and work is done on the system.

### Iso-thermal prcocesses

Systems where the temperature is held constant, usually by connecting the system to a much bigger system whose temperature would need a lot of heat to change. like a heat reservoir.
Since the pressure does actually change this time, you'd need to make a more complex relationship:
$$W = \int P \, dV $$
And you're still calculating work, but you're taking into account the changes in pressure too.
Another difference between isobaric and isothermal processes is that since the temperature is held constant in isothermal processes, the internal energy of the ideal gas cannot change. And thus:
$$\Delta U = Q - W = 0 $$
$$Q = W$$

### Adiabatic processes

This is where no heat is allowed to flow in or out of the system but the gas can expand or be compressed. Thus $Q = 0$, 
$$\Delta U = - W$$

## Second law of thermodynamics

*Because of [[Entropy]], Heat will spontaneously flow from something hotter to something colder, but not from something colder to something hotter.*

Entropy is a measure of the disorder or randomness in a system. The second law of thermodynamics tells us that in any natural process, the total entropy of an isolated system, which includes both the system and its surroundings, will either stay constant or increase but will never decrease. In simpler terms, it means that over time, systems tend to move towards a state of greater disorder.
This law has several implications. One of the key implications is that heat energy tends to disperse or spread out spontaneously. For example, if you have a hot cup of coffee and leave it in a room, the heat from the coffee will gradually transfer to the surrounding air until both reach the same temperature. This is because the energy spreads out to achieve a more uniform distribution, increasing the overall entropy of the system.

Another implication of the second law is the concept of irreversibility. While physical laws usually allow processes to occur in both forward and backward directions, the second law suggests that certain processes, especially those involving energy transfer, are more likely to occur in one direction than in the reverse. For example, a broken egg does not spontaneously reassemble itself because the process of breaking the egg increases the system's entropy, and reversing it would reduce the entropy, which goes against the second law.

It's important to note that the second law of thermodynamics applies to closed or isolated systems, where no energy or matter is exchanged with the surroundings. In open systems, such asw in  living organisms, energy and matter can floand out, allowing for localized decreases in entropy at the expense of increasing entropy elsewhere.