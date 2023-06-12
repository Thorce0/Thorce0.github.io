
<div style="text-align: center;">
<h1> Dev Blog: Enhancing Fish Simulation in Unity with VFX Graph and Compute Shaders </h1>


Hello, fellow developers! 

Today, I'm thrilled to share an exciting project I've been working on
enhancing a fish simulation in Unity using VFX Graph and Compute Shaders. 
The goal was to make the fish appear more organic and to improve their interaction
with the environment.

---

##  Upgrading the Fish Effect

The project started with an existing fish effect implemented using Unity's Particle System.
While this system was functional, it didn't quite capture the organic, fluid movement 
of a school of fish. To address this, I built an effect using Unity's VFX Graph, 
where each fish was influenced by Turbulence Noise. This gave the fish a more natural, 
random movement pattern, enhancing the overall realism of the simulation.


[//]: # (![Turbulence Noise Code]&#40;/images/code-turbulence-noise.png&#41;)

[//]: # (*Code for Turbulence Noise implementation*)

![Before and After Fish Movement](/images/ParticleSystemSwarm.gif)

*Particle System based swarm*

![Before and After Fish Movement](/images/VfxGraphSwarm.gif)

*VFX Graph based swarm*


---

##  Keeping Fish in Check with Unity's SDF Bake Tool

One challenge with the new movement system was preventing the fish from straying 
too far from their intended environment. To solve this, 
I utilized Unity's SDF (Signed Distance Fields) Bake Tool. This tool allows you 
to bake SDFs in Unity, which can then be used to influence particle behavior in
the VFX Graph. In this case, I used SDFs of the corals in the environment to create
boundaries for the fish. This ensured they stayed near the corals and didn't 
swim through them.


![SDF Boundaries](/images/CoralSDF.png)

*SDF Boundaries*


---

##  Implementing a Boid Simulation

While the SDFs helped keep the fish near the corals, the system still 
couldn't prevent collisions between individual fish. To tackle this, 
I implemented a Boid simulation using a Compute Shader. Boid simulations 
are a popular method for creating flocking behavior, and by using a Compute Shader,
I was able to run this simulation on the GPU, greatly improving performance.


[//]: # (![Boid Simulation Code]&#40;/images/code-boid-simulation.png&#41;)

*Code for Boid Simulation*

[//]: # (![Boid Simulation]&#40;/images/boid-simulation.png&#41;)

*Boid Simulation in Action*


---

##  Results and Performance

The final system allowed for a much more complex simulation, with the fish 
moving organically and interacting realistically with their environment. Best of all,
the entire simulation runs on the GPU, meaning the calculations for around 80 fish are
completed in less than 1ms.


![Final Result](/images/BoidSwarm.gif)

*Final Result*


---

This project was a fantastic opportunity to explore the capabilities
of Unity's VFX Graph and Compute Shaders. The results speak for themselves, 
and I'm excited to apply these techniques to future projects.

Stay tuned for more updates, and happy coding! 

Peter

</div>