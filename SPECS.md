# SPECS

## Data

- **Numerical graders**: Per-student scores produced by automated analysis of conversation texts. Each student is a data point; each grader is a feature/dimension.
- **Conversation texts**: Raw chat logs between students and the ChatGPT-based learning tool.
- **Reading ability**: A PII-free metric derived from the student side of conversation texts, serving as the ground-truth outcome variable.

## Pipeline

### Phase 1: Training

1. **Retrieve numerical graders** for all students (students × graders matrix).
2. **Cluster students** using unsupervised clustering on the grader feature space.
   - Method TBD (e.g., k-means, DBSCAN, hierarchical clustering).
   - Target cluster count: 3–15 archetypes.
3. **Retrieve conversation texts** and assign them to clusters matching the grader-based clustering.
4. **Build a digital twin LLM** for each cluster, using that cluster's conversation texts.
   - **Option A — Retrieval-augmented generation (RAG):** Build a vector store per cluster; a general LLM queries it at inference time.
   - **Option B — Post-training:** Fine-tune or otherwise adapt an LLM on each cluster's conversation texts.

### Phase 2: Validation

1. **Estimate reading ability** from students' side of conversation texts using various metrics (methods TBD).
2. **Cluster students by reading ability** using unsupervised clustering on the reading-ability metrics.
3. **Generate twin conversations**: place each digital twin in the same conversational setting and collect synthetic conversation texts, one set per twin/cluster.
4. **Estimate reading ability of twins** by applying the same metrics (from step 1) to twin conversation texts.
5. **Cluster twins by reading ability** using the same clustering method (from step 2).
6. **Compare clusterings**: measure similarity between student clusters and twin clusters.
   - Method TBD (e.g., Adjusted Rand Index, Normalized Mutual Information).

## Open Questions

- Precise unsupervised clustering method for grader-based and reading-ability-based clustering.
- Precise reading-ability estimation metrics from conversation text.
- RAG vs. post-training (or hybrid) for twin construction.
- Method for generating comparable twin conversations (prompt design, conversation simulation).
- Clustering similarity metric for final validation comparison.
