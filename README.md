# Advanced Data Mining

Master-level course of eleven lectures on discovering and critically evaluating patterns in structured, text, and graph data. This follows Neural Architectures and Representation Learning. See the [planned lecture sequence](syllabus/syllabus.md#course-sequence); materials are supplied progressively.

**Start here:** [From Representation Learning to Advanced Data Mining](syllabus/START_HERE_FROM_REPRESENTATIONS_TO_DISCOVERY.md): the course arc and its connection to representations, embeddings, and experimental evaluation.

| Week | Material | Preparation |
|---|---|---|
| 1 | [Data quality and knowledge discovery](weeks/01/Week_01_Data_Quality_Knowledge_Discovery.ipynb) | Read the dataset description; review pandas filtering and grouping. |
| 2 | [Similarity, clustering, and stable patterns](weeks/02/Week_02_Similarity_Clustering_Stable_Patterns.ipynb) | Review Week 1's policy note and the difference between invoice lines and customers. |
| 3 | [Anomalies and review decisions](weeks/03/Week_03_Anomalies_Review_Decisions.ipynb) | Review RFM definitions, representation choices, and the difference between a rare case and a verified error. |

## Local setup

Install [uv](https://docs.astral.sh/uv/getting-started/installation/). Download the complete course folder, then run from its root:

```sh
uv sync --locked
uv run jupyter lab
```

Python 3.12 is used. Choose the environment's Python kernel. Each notebook runs independently, top to bottom, on CPU. Keep `data/` beside `weeks/`. First-time dependency installation needs internet; the core datasets are included.

## Colab setup

Click your session below, connect to a CPU runtime, and choose **Runtime → Run all**. Dependencies install automatically and the dataset is downloaded, verified, and cached by the notebook. No uploads or ZIP extraction are required. If Colab requests a runtime restart after installation, restart and run all again.

- [Open Week 1 in Colab](https://colab.research.google.com/github/rrfhwn/advanced-data-mining-course/blob/main/weeks/01/Week_01_Data_Quality_Knowledge_Discovery.ipynb)
- [Open Week 2 in Colab](https://colab.research.google.com/github/rrfhwn/advanced-data-mining-course/blob/main/weeks/02/Week_02_Similarity_Clustering_Stable_Patterns.ipynb)
- [Open Week 3 in Colab](https://colab.research.google.com/github/rrfhwn/advanced-data-mining-course/blob/main/weeks/03/Week_03_Anomalies_Review_Decisions.ipynb)

## Study and assessment

Each notebook includes a core classroom path, guided experiments, a short reading path, and optional extensions. Weekly TODOs and reports are formative preparation, not additional graded assignments. Four practical assignments contribute 25% each; the overall passing score is 60%. A [draft A1 brief](weeks/03/Assignment_01_Data_Readiness.md) consolidates the initial lectures; use the instructor's confirmed release instructions and deadline, not a draft planning window. Later briefs will be supplied progressively. See the [syllabus](syllabus/syllabus.md).

Weeks 1–3 alternate three 10–15-minute reading-and-reflection windows with independent experiments. Attempt the written checkpoints before opening their self-checks. Choose one route in each practical investigation; the other route is an extension. The explanations are self-contained, so external reading links are for further study.

The supplied retail data is an attributed adaptation under CC BY 4.0. See [data provenance and limitations](data/README.md). Always distinguish observations from interpretations, and preserve the assumptions used to obtain a result.
