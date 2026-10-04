# Yehuda Raanan

**AI Solutions & Deployment · Data & Machine Learning**

I build data and AI solutions around real business problems, combining hands-on work with experience leading teams and establishing new capabilities. My background spans financial modelling, enterprise implementation and applied research. The projects below show how those perspectives meet in decisions about data, system design and what the evidence supports.

## Selected work

### [Text-to-SQL agent and observability](https://github.com/YehudRaanan/mlops-ex2) · AI engineering course project

**Problem.** Organizations work across business domains, and the same question can need different data and context in different units. For example, “How many active customers do we have?” might mean paying customers, recent product users or customers with valid contracts. That is an illustrative business question: a plausible query can still answer the wrong version of it.

**Choices and implementation.** The course project addresses a specific slice of that challenge. Each BIRD request supplies a `db_id` for a preselected SQLite database. Within it, I combined exact-name and semantic table retrieval with one-hop outgoing foreign-key neighbours to bring likely related tables into view without sending the full schema. The agent generates and executes SQL, and can verify and revise the query. Under concurrent load, traces and serving metrics guided changes to worker concurrency, CPU placement of embeddings and schema-embedding caching to improve response time and reliability.

**Evidence.** The saved [baseline](https://github.com/YehudRaanan/mlops-ex2/blob/ex2-local-build/results/eval_baseline.json) and [tuned](https://github.com/YehudRaanan/mlops-ex2/blob/ex2-local-build/results/eval_after_tuning.json) evaluations and the [project report](https://github.com/YehudRaanan/mlops-ex2/blob/ex2-local-build/REPORT.md) document the approach, measured results and questions the agent still answered incorrectly.

### [Reject inference for credit risk](https://github.com/YehudRaanan/reject-inference-credit-risk) · deep learning course project

**Problem.** Rejecting risky borrowers protects a lending portfolio, but rejecting people who would repay also loses opportunities. Because their outcomes are unobserved, it is difficult to assess a different decision rule for that group.

**Choices and implementation.** Home Credit's named application fields made the model inputs understandable in lending terms. I used a simulated score cutoff to keep rejected applicants' true outcomes available for evaluation while hiding them during training. The comparison assessed neural network approaches and CatBoost with both AUC and Precision@20%, which asks how many good borrowers appear in a selected share of the rejected group.

**Evidence.** The [decision log](https://github.com/YehudRaanan/reject-inference-credit-risk/blob/main/docs/decision_log.md) and [final report](https://github.com/YehudRaanan/reject-inference-credit-risk/blob/main/docs/reports/final_report.md) trace a changed conclusion. An initial VIME comparison changed both width and architecture; a later comparison matched the model family and layer depths before revisiting the result.

### [Routing rules and social welfare](https://github.com/YehudRaanan/wardrop-routing-welfare-research)

**Problem.** Navigation guidance changes the traffic it tries to predict. A road operator therefore needs to consider individual incentives, collective responses and tolls together.

**Choices and implementation.** In a controlled two-route SUMO study, I compared moving-average, forward-looking and habitual routing. The analysis measured driver cost, toll effects, mixed adoption and social welfare alongside travel-time outcomes.

**Evidence.** The [paper, simulation and aggregate results](https://github.com/YehudRaanan/wardrop-routing-welfare-research) make the assumptions and comparisons inspectable. In the study's semi-congested setting, the rule with the lowest expected private cost did not have the lowest experienced welfare loss.
