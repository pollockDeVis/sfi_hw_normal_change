## Agent-Based Model of Norm Transitions in a Society

### Introduction

Norm transitions are critical to understanding the evolution of societal behaviors, especially in economic and social contexts. This paper presents an agent-based model (ABM) designed to capture the dynamics of norm transitions within a society. The model simulates how agents' wealth and social norms evolve over time through interactions and wealth generation mechanisms. Our objective is to explore the conditions under which societal norms shift from self-centric to altruistic behaviors and vice versa.

### Model Description
#### Key Assumptions

1. **Agent Characteristics:**
        Initial Wealth and Norms: Each agent starts with a specific amount of wealth and adheres to a norm, which can be either self-centric (focused on personal wealth accumulation) or altruistic (focused on wealth equality).
2. **Wealth Generation:**
        Proportional Income: Agents receive a percentage of their current wealth as income, simulating investment returns.
        Fixed Income: Agents receive a fixed amount of wealth, simulating basic income or wages.
3. **Trade Mechanism:**
        Pairing: Agents are randomly paired for trade at each time step.
        Trade Amount: The wealthier agent offers a trade amount based on a fixed fraction of their wealth.
        Acceptance Criteria: The trade is accepted if it increases the poorer agent's wealth, leading to an update in both agents' wealth.
4. **Norm Transition:**
        Interaction Influence: When a self-centric agent interacts with an altruistic agent, it evaluates if adopting an altruistic norm would increase its utility. If so, the agent may switch to altruistic with a certain probability.
        Spontaneous Transition: Any self-centric agent has a small fixed probability of becoming altruistic spontaneously, regardless of interactions.
5. **Utility Calculation:**
        Self-Centric Utility: Derived purely from the agent's own wealth.
        Altruistic Utility: Higher when the agent's wealth is closer to the average wealth of the population, promoting equality.

 #### Model Dynamics

1. **Initialization:**
        Agent Setup: Agents are initialized with a predefined amount of wealth and a norm (either self-centric or altruistic).
2. **Wealth Generation:**
        Income Calculation: Each agent's wealth increases through both proportional and fixed income sources.
3. **Trade:**
        Interaction: Randomly paired agents trade wealth, benefiting the poorer agent if the trade is accepted based on predefined criteria.
4. **Norm Transition:**
        Evaluation: Agents assess the potential utility of adopting different norms during interactions.
        Spontaneous Change: Agents have a small probability of changing their norms spontaneously.
5. **Simulation Environment:**
        Grid Layout: The society is modeled on a 2D grid where agents interact over a predefined number of steps, allowing for the observation of norm and wealth evolution.

### Key Results

1. **Norm Stability:**
        Persistence: In the absence of significant interactions or spontaneous changes, norms tend to remain stable within the population.
2. **Transition Dynamics:**
        Interaction Influence: High levels of interaction between agents with differing norms can accelerate norm transitions, especially when agents perceive higher utility in adopting a new norm.
        Wealth Inequality: Higher levels of wealth inequality can drive self-centric agents to adopt altruistic norms, as the perceived utility of wealth equality increases.
3. **Utility and Wealth Distribution:**
        Wealth Accumulation: Self-centric agents accumulate wealth more rapidly but may switch to altruistic norms if it offers higher utility in the context of societal wealth distribution.
        Equality Promotion: Altruistic agents contribute to stabilizing wealth distribution, promoting overall societal equality.

### Future Directions

1. **Heterogeneous Agents:**
        Diversity: Introduce varying degrees of wealth generation capabilities and trading propensities among agents to reflect a more realistic population.
2. **Network Structure:**
        Topologies: Explore different network topologies (e.g., small-world networks, scale-free networks) to understand their impact on norm transitions and interactions.
3. **External Shocks:**
        Impact Analysis: Investigate the effects of external shocks (e.g., economic crises, policy changes) on norm stability and transitions within the population.
4. **Cultural Influence:**
        Factors: Incorporate cultural and social factors that might affect agents' propensity to adopt different norms, adding complexity and realism to the model.

### Norm Transitions

* **Easy Norm Transition:**
        Scenario: A society where the majority of agents are self-centric could easily transition to altruistic norms if a significant economic disparity prompts self-centric agents to recognize the utility benefits of altruism. For example, in a scenario of increasing wealth inequality, self-centric agents might adopt altruistic behaviors to stabilize societal conditions and enhance their own utility.
* **Hard Norm Transition:**
        Scenario: A society predominantly altruistic might find it difficult to transition to self-centric norms unless there is a systemic collapse in wealth distribution mechanisms, forcing agents to prioritize personal wealth over societal equality. For instance, in the event of a severe economic downturn that disrupts wealth distribution, altruistic agents might struggle to maintain their norms as they are pressured to focus on personal survival and wealth accumulation.

### Conclusion

The presented agent-based model provides a comprehensive framework to understand how norms transition within a society. By simulating interactions, wealth generation, and norm adoption, the model highlights the conditions under which societal norms shift between self-centric and altruistic behaviors. Future research could expand on this model by incorporating heterogeneous agents, exploring different network structures, and examining the impact of external shocks to gain deeper insights into the dynamics of norm transitions in complex societies.
