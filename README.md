<img src="https://github.com/user-attachments/assets/4fb38def-6618-4de7-b22c-8260aec07e90" width="460" />
<img src="https://github.com/user-attachments/assets/e7289ab2-cc2b-481e-a548-84155e466324" width="460" />

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

## Useful links

- [Value at Risk (VaR) – Wikipedia](https://en.wikipedia.org/wiki/Value_at_risk#Computation_methods)<br>
Background on VaR definitions and classical computation methods

- [Classiq VaR Reference Implementation](https://github.com/Classiq/classiq-library/blob/main/applications/finance/value_at_risk/value_at_risk.ipynb) <br>
Baseline notebook demonstrating a quantum VaR implementation

- [Classiq Documentation](https://docs.classiq.io/latest/) <br>
Reference for the Classiq SDK, modeling language, and analysis tools

- [Quantum Risk Analysis of Financial Derivatives](https://arxiv.org/pdf/2404.10088) <br>
The paper introduces two quantum algorithms to compute Value at Risk (VaR) and Conditional
Value at Risk (CVaR) for portfolios of financial derivatives by encoding many market scenarios
simultaneously on a quantum computer. One approach extends existing quantum risk analysis
techniques, while the other uses a Quantum Signal Processing (QSP) method that requires
fewer quantum resources for the same accuracy. The authors analyze scaling, error behavior,
and show via simulations that quantum methods can reduce resource requirements for tail-risk
estimation.

- [Quantum Subgradient Estimation for Conditional Value-at-Risk Optimization](https://arxiv.org/abs/2510.04736) <br>
This work proposes a quantum method to estimate and optimize CVaR using amplitude
estimation, reducing sample complexity from approximately 1/ε2 to 1/ε. Simulations confirm the
theoretical speedup and robustness to errors in estimating the VaR threshold.

- [Quantum Risk Analysis: Beyond (Conditional) Value-at-Risk](https://arxiv.org/abs/2211.04456) <br>
This paper extends quantum risk analysis beyond VaR and CVaR to alternative measures such
as Expectible VaR (EVaR) and Range VaR (RVaR). It studies robustness under noise and
compares classical and quantum performance, highlighting both advantages and current
hardware limitations.

- [Quantum Risk Analysis](https://arxiv.org/abs/1806.06893) <br>
A foundational paper showing how amplitude estimation enables near-quadratic speedups for
computing VaR and CVaR compared to classical Monte Carlo methods, and discussing
trade-offs between accuracy and circuit complexity.
