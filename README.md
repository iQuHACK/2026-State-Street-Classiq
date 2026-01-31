# iQuHACK 2026 – State Street × Classiq Challenge 
*“Quantum algorithms won’t eliminate uncertainty; but they might finally help us
measure it better.” – State Street × Classiq Team*
<br>

So you fancy taking on the **State Street × Classiq Value at Risk (VaR)** challenge for
iQuHACK 2026?! We welcome you with open arms.<br>

This challenge invites you to explore **how classical and quantum methods estimate
financial risk**, how their **sampling complexities differ**, and under what assumptions
quantum techniques may demonstrate an advantage. You will compute **Value at Risk
(VaR)** using both **classical Monte Carlo** and **quantum amplitude estimation
(QAE/IQAE)** on a controlled, toy probability distribution.
  
## Contents
### Classical Tasks
- Define an asset return probability distribution over a fixed time horizon (e.g. 1 day) ,
starting with a **Gaussian distribution**.
- Use **classical Monte Carlo** to estimate VaR at a chosen confidence level (e.g.,
95%).
- Study how the estimated VaR converge to the theoretical value as a function of the
number of samples.
- Demonstrate the expected **O(1/ε²)** scaling of Monte Carlo error.

### Quantum Tasks
- Encode the same P&amp;L distribution as a **quantum amplitude distribution**.
- Construct a **threshold oracle** that marks tail events (P&amp;L ≤ threshold).
- Implement **Quantum Amplitude Estimation (QAE)** to estimate the tail probability.
- Implement **Iterative QAE (IQAE)** to achieve a target estimation precision.
- Use a **bisection search** over the threshold to determine VaR.
- Demonstrate the expected **O(1/ε)** scaling of quantum amplitudeestimation error.
 
### Comparison &amp; Analysis

- Show how the estimation error ε scales with the number of samples in classical
Monte Carlo, and the number of samples in the quantum approach. Plot **accuracy
vs number of (sample?)** for classical and quantum methods.
- Explore sensitivity to:
    - confidence level (95% vs 99%),
    - discretization resolution,
    - estimation precision,
    - stopping criteria.
- Clearly distinguish **probability estimation error** from **modeling/discretization
error**.

### Optional Extensions
Continue to make clear comparison between the classical and the quantum
approaches.
- Fattailed distributions that better describe return properties of financial assets (e.g.
student’s t distribution).
- Exploration of **CVaR (Expected Shortfall)**.
- Experimentation with ideas from quantum riskanalysis papers. <br>

## Working Environment
This challenge is performed using the **Classiq SDK**. 
All quantum circuits including state preparation, oracle construction, Grover iterations,
and amplitudeestimation routines are built and simulated entirely in Classiq.
 There is **no quantum hardware access** required.
 You are free (and encouraged) to explore different:
- circuitsynthesis strategies,
- oracle designs,
- grid resolutions,
- AE/IQAE parameter choices,
- iterative stopping rules.
 
Your observations about these design choices form an important part of the final
writeup.


## Documentation Requirement
 
Your final writeup should include:
 
- A clear description of the VaR problem and assumptions behind your probability
model.
- An explanation of your classical Monte Carlo workflow.
- A description of your quantum AE/IQAE workflow and bisection search.
- Plots comparing **accuracy vs number of probability queries**.
- Sensitivity analysis covering discretization, precision, and confidence levels.
- A discussion of:
    - when quantum methods appear advantageous,
    - what assumptions enable the advantage,
    - what aspects are asymptotic vs simulator artifacts.

Creativity is encouraged. Tell a story with your methodology, results, and insights.

 
## Submission
To complete your submission:
 
1. Create a teamnamed folder.
2. Include all your code (classical and quantum), notebooks, and utilities.
3. Include either: <br>
   - a `README.md` linking to your writeup, **or** <br>
   - your writeup directly inside the folder.
4. Submit your project according to iQuHACK event instructions and deadlines.
 Make sure your submission is selfcontained and reproducible.

## Evaluation Criteria
Your project will be evaluated on:
1. **Correctness** <br>
Classical and quantum VaR computations should be implemented properly and
consistently.
2. **Quality of Benchmarking** <br>
Clarity and correctness in comparing classical vs quantum estimation, especially
accuracy vs queries.
3. **Technical Depth** <br>
Strength of implementation, use of AE/IQAE, and clarity of modeling assumptions.
4. **Extensions &amp; Creativity** <br>
Additional distributions, confidence levels, risk measures, or methodological
refinements.
5. **Quality of Writeup** <br>
Clear explanations, thoughtful insights, and wellpresented results.

## Key Insight
This challenge is **not** about demonstrating runtime superiority of quantum algorithms
in practice. 
Rather, it is about understanding:
- **how quantum amplitude estimation reduces sampling complexity**, 
- **when this reduction is meaningful**, and 
- **what tradeoffs arise** in implementing quantum riskestimation procedures.<br>

Your goal is to build intuition, not industrial finance pipelines.<br>
Good luck, and happy hacking!