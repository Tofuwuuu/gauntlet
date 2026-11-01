# How Well Do AI Code Checkers Catch Bugs? A Benchmark of Pre-Merge Verification Tools on Agent-Generated Code

## Chapter 1: Introduction (draft)

### 1.1 Background of the Study
AI coding agents now write a large share of new code. GitHub's Octoverse 2026 report states that by September 2026, more than 40% of pull requests on GitHub started with an agent's first draft, up from 17% in March of the same year.

Developers do not take this code on faith. In the Stack Overflow Developer Survey 2026, 76% of developers said they check AI output by running it locally, 64% compare it with the existing codebase, and 53% check tests or security implications. Only 10% use AI answers as-is.

To reduce this manual work, a new class of pre-merge verification tools has appeared. Tools such as ForgeBench, NEKOWORK and augur read an AI-generated change and return a verdict such as pass, review or block. Research tools go further: Tracer (2026) placed the vulnerable code in the review scope for 94.6% of agent patches on the SusVibes benchmark, compared with 13.4% for a conventional scanner warning.

### 1.2 Statement of the Problem
Each verification tool reports results on its own chosen tasks and metrics. No shared benchmark tests these tools against the same set of faulty AI-generated patches. As a result, developers and teams cannot tell which tool catches the most real bugs, which raises the fewest false alarms, or which fits their workflow.

### 1.3 Objectives of the Study
General objective: to build an open benchmark and use it to compare pre-merge verification tools on agent-generated code.

Specific objectives:
1. To assemble a dataset of AI-generated patches with known bugs, drawn from public benchmarks and supplemented with faulty patches written by the researcher.
2. To run selected verification tools on the same dataset under the same conditions.
3. To measure each tool's bug detection rate, false alarm rate and run time.
4. To release the dataset and evaluation scripts as an open-source repository.

### 1.4 Significance of the Study
Developers gain evidence for choosing a checker instead of relying on each vendor's own claims. Tool builders gain a common test to measure and improve against. Researchers gain a reusable dataset for future work on AI code review.

### 1.5 Scope and Limitations
The study covers publicly available verification tools that can run locally or on free tiers. It uses only public code and synthetic faulty patches; no private or proprietary code is used. Programming languages are limited to those the selected public benchmarks cover. Results reflect tool versions available at the time of testing.

### Sources
- GitHub, Octoverse 2026: https://github.blog/news-insights/octoverse/octoverse-commits-pushes-reach-new-highs-in-2026-as-developers-build-with-agents/
- Stack Overflow Developer Survey 2026, AI: https://survey.stackoverflow.co/2026/ai/data/ai-work-next
- Tracer (arXiv 2610.34098): https://arxiv.org/abs/2610.34098
- ForgeBench: https://forgebench.dev/
- NEKOWORK: https://github.com/Ps-Neko/NEKOWORK/
- augur: https://github.com/CorvidLabs/augur
