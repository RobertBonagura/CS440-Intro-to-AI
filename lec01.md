# Lecture 1 - The Foundations of AI and Intelligent Agents

## What is Artificial Intelligence?
* Acting Humanly
    * The Turing Test - is the ability for a machine to act intelligently enough to pass as being indistinguishable from a human being.
    * Requires:
        * Natural language processing
        * Knowledge representation
        * Automated reasoning
        * Machine learning
* Thinking Humanly
    * The focus of cognitive science - requires experimental investigation on actual humans or animals.
* Thinking Rationally
    * Logic-based AI, which allows for the creation of intelligent systems that reason using syntax and laws of logic
* Acting Rationally
    * the action that achieves the best outcome

## AI Problem definition
1. An environment - The world in which the problem takes place
2. Perceptions/Observations -  Inputs the agent receives
    * Convention:
        * Let **O** be the set of all possible obsvervations.
        * Let **o** e **O** refer to an individual observation.
3. Actions - Operations the agent can perform
    * Convention:
        * Let **A** be the set of all possible actions.
        * Let **a** e **A** refer to an individual action.
4. Evaluation - Feedback
    * Can be a positive or negative value.
---
## Different Agents
**Reflex Agents**
* What is the world like now?
* What action should I do now? (based on **condition-action rules**)

**State** - 
A data structure representing the environment. It incorporates all relevant information.

**Model-based Reflex Agents**
* What is the world like now? (Based on **state** and knowledge of how the world evolves and what my actions do).
* What action should I do now? (based on condition-action rules)

**Goal-based Agents**
* What is the world like now? (Based on state and knowledge of how the world evolves and what my actions do) 
* **What will the world be like if I do action A**.
* What action should I do now? (based on **Goals**)

**Utility function** - How the agent should assign a utility value top each state
<br>Convention:
    Let **r(s)** define the utility of state **s** 

**Utility-based Agents**
* What is the world like now? (Based on state and knowledge of how the world evolves and what my actions do)
* What will the world be like if I do action A
* **How happy will I be in the state**, based on my **Utility**?
* What action should I do now?

**Learning Agents**
* Evaluate State
* Learning element
* Performance generator
* Problem generator
---
## Environments and their Properties

**Fully observable vs partially observable**<br>
If the agent always has access to the complete state of the environment, then the environment is fully observable.

**Deterministic vs stochastic**<br>
If the next state is completely determined by the current state and the the agent's actionm then the environment is determinstic.<br>
If the the environment is determinstic except from the actions of other agents, then it is called strategic.

**Episodic vs sequential**<br>
In an episodic environment, the agent's experience does not depend the actions taken in previous episodes.<br>
In sequential, the current decision could affect all future decisions.

**Static vs dynamic**<br>
If the environment changes while the agent is not acting, then the environment is dynamic

**Discrete vs continuous**<br>
Continuous values can appear in the state of the environment, time, in the perceptions or actions of the agent.

**Single agent vs multiagent**<br>
Multiagent environments include Competitive and Cooperative environments.
