## Brain Function Components 

Brains don't split into clean modules, but if we named components the way an engineer would, the functional "departments" would look roughly like this:

**Input (sensors)**

- **Vision** — the visual cortex system (occipital lobe and beyond)
- **Audition** — sound processing and speech-sound decoding
- **Touch & body sense (somatosensation)** — pressure, temperature, pain
- **Smell (olfaction)** and **Taste (gustation)**
- **Interoception** — sensing internal states like heartbeat, hunger, breath

**Output (actuators)**

- **Motor control** — movement planning and execution (motor cortex, cerebellum, basal ganglia)
- **Speech production** — turning language into sound

**Processing & storage**

- **Language module** — both comprehension (Wernicke's area) and production (Broca's area)
- **Working memory** — the short-term scratchpad (prefrontal cortex)
- **Long-term memory** — episodic (events), semantic (facts), procedural (skills, habits)
- **Spatial navigation** — the internal GPS (hippocampus)

**Control & regulation**

- **Executive function** — planning, decision-making, impulse control (prefrontal cortex)
- **Attention** — the spotlight/filter system
- **Emotion engine** — threat detection, emotional tagging (amygdala, limbic system)
- **Reward & motivation** — dopamine-driven wanting and learning
- **Autopilot** — breathing, heart rate, sleep cycles (brainstem, hypothalamus)

**Higher-order**

- **Social cognition** — reading faces, intentions, theory of mind
- **Self & introspection** — the default mode network, active when you daydream or reflect

The big caveat: real brains are more like overlapping networks than Lego bricks — vision, memory, and emotion all talk to each other constantly. But as a naming scheme, that's the decomposition most neuroscientists would recognize.

"build a brain out of AI agents." Here's how I'd staff each department with the agent best suited to the job:

**Sensors**

- **Vision** → a vision model (like a ViT / multimodal image model) — trained on pixels, great at compression of scenes into meaning
- **Audition** → a speech-to-text + audio model (Whisper-style)
- **Touch & body sense** → a sensor-fusion model — the kind used in robotics
- **Interoception** → a small predictive model (like the ones in wearables guessing your HRV, stress, sleep phase)

**Output**

- **Motor control** → a reinforcement learning agent with fine-grained continuous control (this is what powers robot locomotion) — you do *not* want an LLM balancing your body
- **Speech production** → a text-to-speech agent with low latency

**Processing & storage**

- **Language module** → an LLM, obviously — the flagship agent of the whole system
- **Working memory** → the LLM's context window, or a scratchpad agent
- **Long-term memory** → a retrieval agent (vector database + embedding search) — the hippocampus of every serious AI system today
- **Spatial navigation** → a world-model / spatial-reasoning agent (pathfinding, SLAM in robotics)

**Control & regulation**

- **Executive function** → an orchestrator/planner agent — the one that decomposes goals into steps, calls the other agents, and vetoes bad plans
- **Attention** → the transformer attention mechanism itself... or a router agent deciding which agent gets to speak
- **Emotion engine** → a fast classifier (threat/salience tagging) — small, reactive, not very smart — which is accurate to the amygdala
- **Reward & motivation** → the training objective / reward model — the agent nobody sees but that shapes everything
- **Autopilot** → a fixed control loop, not an agent at all — like the code in a pacemaker

**Higher-order**

- **Social cognition** → a theory-of-mind agent — a model dedicated to inferring other agents' beliefs and goals
- **Self & introspection** → a monitoring/critique agent that watches the system's own outputs and asks "why did I do that?"

The fun part of the mapping: it inverts the usual hype. The LLM (language) isn't the brain — it's one department. The actual "self" is the quiet orchestrator plus the introspection agent, and the reward model is arguably the most powerful agent in the building, because it decides what everyone else optimizes for.