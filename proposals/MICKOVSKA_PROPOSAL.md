# Paper Proposal Submission

## 1. Student Information
* **Name:** Eleni Mickovska
* **PhD Study Program:** Environmental Earth Sciences, specialization Environmental Modelling
* **Dissertation Topic Summary:** My research develops an integrated modelling framework for adaptive water-resources management in the Ohře River basin, Czech Republic. It combines sectoral water-use modelling with a basin-scale Pywr representation of hydrology, infrastructure and management constraints, followed by reinforcement learning (RL) for adaptive multi-objective operation and decision support.

## 2. Paper Details
* **Paper Title:** Tree-based fitted Q-iteration for multi-objective Markov
decision processes in water resource management
* **Authors:** F. Pianosi, A. Castelletti and M. Restelli
* **Year & Journal:** 2013, Journal of Hydroinformatics, 15(2), 258–270
* **DOI / Link:** https://doi.org/10.2166/hydro.2013.169

## 3. Methodological Focus
* **Core Statistical/Algorithmic Methods to Implement:** 
  * Batch-mode Fitted Q-Iteration (FQI), using Extremely Randomized Trees to approximate the action-value function from offline state-action transition samples.
  * Multi-objective Fitted Q-Iteration (MOFQI), including the construction of an augmented training dataset using objective-preference weights, linear scalarisation of vector-valued rewards and approximation of a weight-conditioned action-value function.
  * Extraction and evaluation of operating policies for different objective-preference weights.
  * Comparison of a single MOFQI training process with repeated standard FQI training processes across several prescribed objective-weight combinations.

## 4. Technical Implementation Strategy
* **Target Language:** [ ] R | [x] Python | [ ] C++
* **Target Output:** An installable Python package with a documented API, automated tests and a Jupyter notebook demonstrating the paper’s synthetic two-objective reservoir test case.
* **Key Dependencies planned:** NumPy, pandas, scikit-learn, Matplotlib, Jupyter and pytest.
* **Validation Strategy:** Unit tests will verify reward scalarisation, construction of FQI and MOFQI Bellman targets, objective-weight augmentation, action selection, policy extraction and reservoir mass balance. The accompanying notebook will implement the synthetic reservoir dynamics and the flood-control and irrigation-supply objectives described in the paper. Using fixed random seeds, policies obtained from one MOFQI model will be compared with policies obtained from repeated FQI models across several objective-weight combinations. Validation will focus on the correctness of the algorithmic implementation and qualitative reproduction of the objective trade-offs reported in the paper, rather than exact reproduction of the published numerical values. The paper’s custom t-test-based Extra Trees pruning modification, stochastic dynamic programming reference implementation, exact reproduction of Table 1 and the real-world Hoa Binh case study are outside the proposed scope.
