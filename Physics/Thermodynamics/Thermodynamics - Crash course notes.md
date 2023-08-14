
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

Because of [[Entropy]], Heat will spontaneously flow from something hotter to something colder, but not from something colder to something hotter.