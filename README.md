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
### Detailed Model Setup

#### Initialization Phase

1. **Agent Setup**:
   - **Initial Wealth**: Each agent is initialized with a predefined amount of wealth. The distribution of this initial wealth can be equal, unequal, highly unequal, or normally distributed. The chosen distribution method influences the initial conditions of wealth inequality in the society.
   - **Behavior Norms**: Agents are assigned one of two behavioral norms: self-centric (selfish, norm = 0) or altruistic (norm = 1). The proportion of altruistic agents is determined by a predefined ratio, reflecting the tendency of individuals towards altruism or self-interest in the population.

#### Wealth Generation

2. **Income Calculation**:
   - **Proportional Income**: Each agent's wealth increases proportionally based on a growth rate defined in the model. This simulates economic growth or returns on investment, allowing wealth to compound over time.
   - **Fixed Income**: Agents receive a fixed amount of income, simulating a salary from employment. This fixed income is added to the agent's wealth each step, reflecting the regular earnings from a job, which may vary depending on the agent's employment status.

#### Trade

3. **Interaction**:
   - **Random Pairing**: Agents randomly select a neighbor for trade interactions. If an agent has no neighbors, no trade occurs. This random pairing reflects the stochastic nature of market interactions or social exchanges.
   - **Wealth Transfer**: During trade, agents transfer a predefined proportion of their wealth to the selected neighbor. This transfer simulates market transactions or resource sharing, where the wealthier agent's trade benefits the poorer agent if the trade criteria are met.

#### Norm Transition

4. **Evaluation**:
   - **Norm Evaluation**: Agents assess the potential utility of adopting different norms based on interactions with their neighbors. If a majority of an agent's neighbors adhere to a particular norm, the agent may consider changing its own norm to align with the predominant behavior, reflecting social conformity pressures.

5. **Spontaneous Change**:
   - **Spontaneous Norm Change**: Agents have a small probability of changing their norms spontaneously, independent of their interactions. This models the possibility of individual behavioral changes due to personal experiences or intrinsic motivations.

#### Simulation Environment

6. **Complex Network Layout**:
   - **Small-World Network**: The society is modeled using a small-world network, such as the Watts-Strogatz model, where agents are nodes connected by edges representing social or economic ties. This network structure captures the characteristics of real-world social networks, including short path lengths and high clustering, which facilitate both local and global interactions.
   - **Simulation Steps**: The simulation runs over a predefined number of steps, allowing for the observation of the evolution of norms and wealth distribution over time. Each step consists of agents performing their behavior logic in sequence, including wealth generation, expenditure, trade, wealth transfer, and social influence.

#### Data Collection and Model Execution

7. **Gini Coefficient Calculation**:
   - **Inequality Measure**: The Gini coefficient is used to quantify the level of wealth inequality within the society. This coefficient is calculated based on the Lorenz curve and numerical integration, providing a measure of disparity in wealth distribution among agents.

8. **Data Collection**:
   - **Data Collector**: The model employs a data collector (DataCollector) to record various metrics at each simulation step. This includes the Gini coefficient and individual agent attributes such as wealth and behavioral norms, enabling detailed analysis of the simulation outcomes.

9. **Model Step**:
   - **Sequential Updates**: In each simulation step, the model collects data and updates the state of all agents. This includes generating wealth, making expenditures, trading with neighbors, transferring wealth, and experiencing social influence, reflecting the dynamic interactions and economic activities in the society.

10. **Model Run**:
    - **Simulation Execution**: The model is executed for a specified number of steps, with the simulation running iteratively to study the effects of different parameters on social dynamics. By varying initial conditions and model parameters, researchers can explore how different factors influence wealth distribution and behavioral norms over time.

By following this detailed setup, the model simulates the dynamic processes of wealth generation, consumption, trade, wealth transfer, and social influence within a society. This allows for the investigation of how various factors impact wealth inequality and the evolution of behavioral norms.


### Key Results

1. **A change of norm with different ratio of altruistic agents**
Basic Parameter Setting
```python
params = {
    "num_agents": 100, # Can increase this
    "avg_node_degree": 4,
    "rewiring_prob": 0.1,
    "initial_wealth": 100, # Can be heterogenous
    "growth_rate": 0.01,
    "trade_ratio": 0.05,
    "salary": 1, # This can vary
    "expenditure": 5,
    "donation_ratio": 0.01,
    "ratio_of_altruistic_agents": 0.1, # Main thing that we change #0.152 to 0.153
    "wealth_distribution": "equal"
}
```

* Equal Model
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/d2df1f71-6397-427e-878c-be4a5a51701b">
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/f52193c6-13a1-47fd-a1e8-59d2b45737bd">
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/2ea45e84-a3b4-4a11-98e7-60fcf230a58a">
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/dd28343f-ea88-4d9d-9377-8d916c4fd8ac">

* UnEqual
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/cf7aa2a2-99d1-4e1e-84e4-478fcf4846b5">

* Very UnEqual
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/59c0c543-d1e5-449e-a0e3-ee4ffb1f1a44">

* Normal
<img width="400" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/244e9321-5e04-4fab-b4c4-10392e7433c6">

Around 0.153 in the model is the key point that causes the norm transition. However, this critical point does not always occur stably. That is, the proportion of the number of altruistic actors in the population that will determine whether a norm transition occurs is around 15%.

2. **Gini Coefficient over Time**
<img width="300" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/f387e136-25ce-416e-941f-641eb1bf73e5">
<img width="300" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/5ef014b1-9c5e-4b52-bce0-53cd610c67c8">
<img width="300" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/38638a6b-6daa-4994-a80b-69bf44f942e0">
The Gini coefficient reflects the gap between the rich and poor of the group, and although they all eventually converge to 0, groups that do not undergo a norm transition will at some point produce a sudden rise in the Gini coefficient, followed by a sharp drop to stabilize at 0. (Does this make sense?)

3. **Norm Transition in Network**
Take the Equal model as an example, choose the model where a norm transition has occurred, and observe how the norm transitions through the small-world network. initially set the percentage of altruistic in the population to 0.16, with red for selfish and blue for altruistic.

<img width="200" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/97fffb66-f8b2-4379-b3dd-8471eae04666">
<img width="200" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/2ced9e78-3970-48b9-84b1-3795f1585bf8">
<img width="200" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/06305958-681f-434f-ab73-fd6aad8858f0">
<img width="200" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/225d70c9-8065-4794-83c6-ef2cf5495093">
<img width="200" alt="图片" src="https://github.com/pollockDeVis/sfi_hw_normal_change/assets/114042177/943630df-60cb-493c-ae50-c0a41e84dd79">


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
