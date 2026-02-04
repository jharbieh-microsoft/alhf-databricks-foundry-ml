# Agent Learning from Human Feedback (ALHF) Research
## Azure AI Foundry & Azure Machine Learning Support Analysis

This repository contains comprehensive research and implementation guidance for implementing Agent Learning from Human Feedback (ALHF)— a technique pioneered by Databricks — using Microsoft Azure's AI stack, specifically Azure AI Foundry and Azure Machine Learning Studio.


## 📋 Overview

This research investigates whether Microsoft's Azure AI platform provides equivalent capabilities to Databricks' ALHF methodology, which enables agents to learn and improve from lightweight natural-language human feedback with minimal supervision.

### Key Finding

Yes, Azure AI Foundry supports ALHF-style agent improvement loops, though the implementation differs from Databricks' approach. Azure provides:

- ✅ Human evaluation templates for structured feedback collection
- ✅ Synthetic evaluators for automated assessment (intent, tool accuracy, safety, groundedness)
- ✅ End-to-end observability with Application Insights integration
- ✅ AI Red Teaming for adversarial testing
- ✅ Fine-tuning pipelines for model improvement
- ⚠️ No automatic agent retraining (requires manual implementation of the feedback loop)


## 📁 Repository Contents

### 1. alhf-databricks-foundry-ml-research.md
Detailed analysis comparing Databricks ALHF with Azure AI Foundry capabilities, including:
- What Databricks ALHF provides
- Azure AI Foundry's equivalent features
- Gap analysis and workarounds
- Integration with Azure Machine Learning Studio

### 2. alhf-databricks-foundry-ml-blueprint.md
Practical implementation blueprint for creating ALHF-style agent improvement loops in Azure AI Foundry:
- 7-step implementation guide
- Human feedback capture strategies
- Synthetic evaluation configuration
- Training dataset construction
- Fine-tuning and policy optimization approaches
- Continuous evaluation loop design
- Visual architecture diagrams (text-based)

### 3. alhf-databricks-foundry-ml-slides.md
Presentation-ready slide deck covering:
- Conceptual architecture of human-feedback driven agent improvement
- Step-by-step implementation walkthrough
- Azure AI Foundry and Azure ML Studio integration
- Multi-agent workflow extensions
- Recommended operating model
- Production deliverables checklist

### 4. alhf-databricks-foundry-ml.md
Quick reference document with curated links and resources organized by topic.

### 5. slides/ (Interactive Presentation)
RevealJS-based interactive slideshow for presenting the ALHF implementation:
- index.html - Complete presentation with 17+ slides
- README.md - Documentation and usage instructions

## 🎬 Interactive Slideshow

This repository includes a RevealJS-based interactive presentation in the `slides/` folder that you can use to present the ALHF implementation approach.

### Quick Start

#### Option 1: Direct Browser Access
```powershell
# Open directly in your default browser
start slides/index.html
```

#### Option 2: Local Web Server (Recommended)
```powershell
# Using Python
cd slides
python -m http.server 8000

# Then open: http://localhost:8000
```

#### Option 3: VS Code Live Server
1. Install the "Live Server" extension in VS Code
2. Right-click on `slides/index.html`
3. Select "Open with Live Server"

### Slideshow Features
- ✅ 17+ professionally styled slides
- ✅ Custom Azure AI branding (#0078d4, #50e6ff)
- ✅ Interactive navigation with keyboard controls
- ✅ Visual flow diagrams and architecture
- ✅ Responsive design for all devices
- ✅ Speaker notes support (press 'S')
- ✅ Overview mode (press 'Esc')
- ✅ No installation required - all dependencies via CDN

### Keyboard Controls
- **→ / ←** or Space- Navigate slides
- **Esc** - Slide overview
- **F** - Fullscreen mode
- **S** - Speaker notes view
- **B** - Pause (black screen)

## 🎯 Core Concepts

### Databricks ALHF
Agent Learning from Human Feedback (ALHF) is a technique that enables agents to continuously improve through:
- Lightweight natural-language feedback from humans
- Minimal supervision requirements
- Rapid adaptation to new patterns
- Structured assessment objects stored in MLflow

### Azure AI Foundry ALHF-Style Implementation
Azure replicates ALHF concepts through:
1. Human Evaluation Templates — structured feedback collection (thumbs up/down, sliders, multiple choice, free-text)
2. Synthetic Evaluators — automated assessment of intent resolution, tool-call accuracy, task adherence, groundedness, and safety
3. Observability Stack — traces, spans, tool logs integrated with Application Insights
4. Training Dataset Construction — combining human + synthetic feedback with expected outputs
5. Model Improvement — fine-tuning, prompt optimization, or policy updates
6. Continuous Evaluation Loop — re-assessment after improvements
7. Multi-Agent Extensions — per-agent evaluators and handoff quality scoring

## 🏗️ Implementation Architecture

```
┌───────────────────────────────────────────┐
│     1. Build Agent in Azure AI Foundry    │
│   (Model + Tools + Policies + Boundaries) │
└───────────────┬───────────────────────────┘
                ↓
┌───────────────────────────────────────────┐
│    2. Enable Observability & Logging      │
│  (Traces, Spans, Tool Calls, App Insights)│
└────────────────┬──────────────────────────┘
                 ↓
┌───────────────────────────────────────────┐
│   3. Collect Human Feedback (ALHF-style)  │
│  - Human Evaluation Templates             │
│  - Reviewer Scoring Interface             │
└────────────────┬──────────────────────────┘
                 ↓
┌───────────────────────────────────────────┐
│  4. Run Automated + Synthetic Evaluators  │
│  - Intent, Tool Accuracy, Safety Checks   │
│  - AI Red Teaming (PyRIT)                 │
└────────────────┬──────────────────────────┘
                 ↓
┌───────────────────────────────────────────┐
│    5. Build Unified Training Dataset      │
│ (Feedback + Expected Outputs + Traces +   │
│  Error Classifications)                   │
└────────────────┬──────────────────────────┘
                 ↓
┌───────────────────────────────────────────┐
│     6. Apply Improvements                 │
│  - Fine-tuning (Azure ML Studio)          │
│  - Prompt/Policy Optimization             │
│  - Workflow Logic Updates                 │
└────────────────┬──────────────────────────┘
                 ↓
┌───────────────────────────────────────────┐
│    7. Continuous Evaluation Loop          │
│  (Re-evaluate → Analyze → Iterate)        │
└───────────────────────────────────────────┘
```

## 🔧 Azure Components

### Azure AI Foundry
- Agent Development Platform — Base model selection (GPT-4o, GPT-4 Turbo, Phi-3, etc.)
- Human Evaluation System — Native templates for collecting structured feedback
- Synthetic Evaluators — Intent resolution, tool-call accuracy, task adherence, groundedness, safety
- Observability — Full trace and span logging with tool-call monitoring
- Multi-Agent Workflows — Support for complex agent orchestration
- AI Red Teaming — PyRIT integration for adversarial testing
- Evaluation Blade — Comprehensive evaluation management interface

### Azure Machine Learning Studio
- Automated ML (AutoML) — Automatic model selection and hyperparameter tuning
- Hyperdrive — Distributed hyperparameter optimization
- MLOps Pipelines — Automated retraining, drift monitoring, deployment
- Model Registry — Version management and model governance
- Responsible AI Tools — Fairness, explainability, and error analysis

### Integration Pattern
- Foundry handles agent-level behavioral learning and evaluation
- Azure ML Studio handles model-level optimization and lifecycle management
- Together they create a complete ALHF-style closed-loop system

## 🚀 Implementation Steps

### Phase 1: Foundation
1. Define agent in Azure AI Foundry (model, tools, system message)
2. Enable Application Insights and agent observability
3. Configure evaluation blade access

### Phase 2: Feedback Collection
4. Create human evaluation templates (thumbs, sliders, multiple choice, free-text)
5. Enable feedback capture during agent preview
6. Export and store feedback data with trace IDs

### Phase 3: Automated Assessment
7. Configure built-in synthetic evaluators
8. Set up AI Red Teaming for adversarial testing
9. Establish safety and risk scorecards

### Phase 4: Data Consolidation
10. Aggregate human feedback, synthetic scores, and traces
11. Build unified training dataset with columns:
    - Input
    - Agent output
    - Human expected output
    - Feedback scores
    - Error classification
    - Context retrieval artifacts

### Phase 5: Improvement
12. Choose improvement strategy:
    - Option A: Fine-tune model using Azure ML Studio
    - Option B: Optimize prompts, policies, and guardrails
    - Option C: Update workflow logic and state machines
13. Deploy improved agent

### Phase 6: Continuous Loop
14. Re-run synthetic evaluators
15. Collect new human feedback
16. Monitor Application Insights for regressions
17. Iterate until metrics meet targets

## 📊 Recommended Operating Model

| Activity | Frequency | Responsible Team |
|----------|-----------|------------------|
| Human Evaluation | Weekly | SMEs, Domain Experts |
| Synthetic Evaluation | Continuous | Automated Pipeline |
| Red Teaming | Monthly | Security Team |
| Fine-Tuning Cycle | Monthly | ML Engineering |
| Observability Monitoring | Real-time | DevOps/SRE |
| Policy Updates | As Needed | Product/Governance |

## 🎓 Use Cases

This research and implementation blueprint supports:

- Proof of Concept (POC) → Pilot → Production agent lifecycle acceleration
- Agent governance frameworks for enterprise compliance
- Evaluation strategy workshops and capability demonstrations
- Azure AI Foundry adoption for agent-based solutions
- ALHF-style iterative learning implementation in Azure
- Multi-agent orchestration with quality assurance

## 🔍 Key Differences: Databricks ALHF vs. Azure AI Foundry

| Capability | Databricks ALHF | Azure AI Foundry |
|------------|-----------------|------------------|
| Human Feedback Collection | ✅ MLflow assessment objects | ✅ Human Evaluation Templates |
| Lightweight Feedback | ✅ Natural-language annotations | ✅ Structured questions (thumbs, sliders, text) |
| Automatic Agent Retraining | ✅ Built-in learning loop | ⚠️ Manual implementation required |
| Synthetic Evaluators | ✅ Custom evaluators | ✅ Built-in suite (intent, tools, safety, groundedness) |
| Observability | ✅ MLflow tracing | ✅ Application Insights + Agent traces |
| Red Teaming | ⚠️ Manual setup | ✅ PyRIT integrated |
| Fine-Tuning Integration | ✅ Seamless with Databricks | ✅ Via Azure ML Studio |
| Multi-Agent Support | ✅ Via MLflow | ✅ Native multi-agent workflows |
| Enterprise Scale | ✅ Databricks lakehouse | ✅ Azure cloud ecosystem |

## 📚 Links, References & Resources

### Databricks ALHF Resources
- [Agent Learning from Human Feedback (Substack)](https://machinelearningatscale.substack.com/p/agent-learning-from-human-feedback)
- [Databricks ALHF Case Study - Knowledge Assistant](https://www.databricks.com/blog/agent-learning-human-feedback-alhf-databricks-knowledge-assistant-case-study)
- [Databricks MLflow Human Feedback Documentation](https://learn.microsoft.com/en-us/azure/databricks/mlflow3/genai/human-feedback/)

### Azure AI Foundry Documentation
- [Azure AI Foundry vs Azure Databricks - Unified Enterprise Intelligence Approach](https://techcommunity.microsoft.com/blog/microsoftmissioncriticalblog/azure-ai-foundry-vs-azure-databricks-%E2%80%93-a-unified-approach-to-enterprise-intellig/4467576)
- [Evaluate Generative AI Applications in Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/evaluate-generative-ai-app?view=foundry-classic)
- [Human Evaluation in Azure AI Foundry Observability](https://learn.microsoft.com/en-us/azure/ai-foundry/observability/how-to/human-evaluation?view=foundry)
- [Agent Evaluation SDK for Azure AI Foundry](https://learn.microsoft.com/en-us/azure/ai-foundry/how-to/develop/agent-evaluate-sdk?view=foundry-classic)
- [Azure AI Foundry Observability Overview](https://learn.microsoft.com/en-us/azure/ai-foundry/observability/overview?view=foundry)

### Azure Machine Learning Resources
- [Evaluate Model in Azure Machine Learning](https://learn.microsoft.com/en-us/azure/machine-learning/component-reference/evaluate-model?view=azureml-api-2)
- [The Signals Loop: Fine-Tuning for World-Class AI Apps and Agents](https://azure.microsoft.com/en-us/blog/the-signals-loop-fine-tuning-for-world-class-ai-apps-and-agents/)

### NOTICES
- [Feedback model (deprecated)](https://learn.microsoft.com/en-us/azure/databricks/generative-ai/agent-framework/feedback-model)

## 📝 License

This research is provided for informational and educational purposes.

## ⚡ Quick Start Summary

To implement ALHF-style agent learning in Azure:

1. Start with Azure AI Foundry for agent development and evaluation
2. Enable observability from day one
3. Create human evaluation templates for structured feedback
4. Configure synthetic evaluators for automated assessment
5. Integrate Azure ML Studio for model-level optimization
6. Build the feedback loop combining human + synthetic data
7. Iterate continuously with regular evaluation cycles

The result is a production-ready agent improvement pipeline that rivals Databricks ALHF capabilities while leveraging Azure's enterprise-grade infrastructure and governance.
