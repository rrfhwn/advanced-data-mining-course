# From Representation Learning to Advanced Data Mining

Data can contain useful patterns without making them easy to recognize. Purchases may reveal recurring combinations of products. Documents may share a theme despite using different words. A network may contain closely connected groups. An unusual observation may reveal a recording error, an important event, or a legitimate exception.

Advanced Data Mining is about discovering these patterns and understanding what they mean. It combines data exploration, representations, algorithms, and critical interpretation. The aim is to move from “the program found something” to an explanation of what was found, why it might matter, and how strongly the evidence supports it.

## The connection to representation learning

In *Neural Architectures and Representation Learning*, a central idea is that a model transforms its input into a representation useful for a task. A convolutional network turns pixels into features. A sequence model carries information across inputs. A transformer builds representations that depend on context. These transformations influence which similarities and differences a model can recognize.

That idea is equally important in data mining. Before comparing observations, we decide how to describe them. A customer might be represented by spending, purchase frequency, or product preferences. A document might be represented by word counts or a learned embedding. An object in a network might be described by its own attributes, its connections, or both.

Consider two customers who have each spent £500. They are identical if total spending is the only feature. But one might have made a single purchase while the other made twenty smaller purchases. Adding frequency makes that difference visible. Adding product categories might reveal another distinction: similar spending can correspond to very different interests.

There is therefore no single, context-free answer to “are these observations similar?” Similarity depends on the representation and the question. This course develops that connection through investigations across several kinds of data.

| Idea from representation learning | Its role in data mining |
|---|---|
| Features preserve some information and discard other information | Choose attributes that make relevant patterns visible; inspect what the choice leaves out. |
| Embeddings place observations in a vector space | Search, compare, and group documents using learned similarity. |
| Model behavior depends on data and design choices | Examine how sampling, preprocessing, and method settings affect discovered patterns. |
| A single score can hide important failures | Inspect examples and alternative explanations alongside summary metrics. |
| Evaluation should be separate from model selection | Check selected patterns on evidence that did not drive their discovery. |

Neural representations are one useful tool in this process. Other questions are better served by simple numerical features, explicit item sets, word-based representations, or graphs. Comparing these choices helps explain when additional complexity is worthwhile.

## From records to a useful question

Imagine an online shop with invoice lines, product descriptions, and customer identifiers. We might investigate which products occur together, which customers have similar purchasing histories, which descriptions refer to similar products, or which invoices deserve review.

These questions use different observation units. A product line is not an entire invoice, and an invoice is not a customer. Combining lines into invoices or invoices into customer histories changes what each observation represents. That decision comes before the algorithm, but it can have just as much influence on the result.

Data quality also depends on the intended use. A missing customer identifier may prevent a record from contributing to a known customer's history while still allowing it to contribute to a sales total. A negative quantity may correctly record a return. A repeated row may be an export error or a legitimate event whose distinguishing identifier is absent. Preparation requires understanding the records, not simply making the table look tidy.

Later methods inherit these consequences. Duplicate transactions can inflate a rule's apparent frequency. Duplicate documents can distort topic discovery or retrieval evaluation. A graph built from uncertain relationships can produce precise-looking results whose meaning remains unclear.

## The course arc

### Understand the data and explore its structure

The course begins with a reliable way to approach an unfamiliar dataset: identify the observation unit, inspect quality and coverage, explore distributions, and document consequential choices. Comparing plausible preparation policies reveals whether a conclusion depends on one particular decision.

Similarity and clustering extend this investigation. Scaling can change which observations are close; different features can produce different groups. A projection can make a pattern easier to see while hiding information from the original space. Clusters are treated as possible descriptions of structure, examined through their examples and stability.

### Discover recurring combinations

Association rule mining examines items that occur together in transactions. “Purchases containing A often contain B” can sound useful, but its meaning depends on the baseline. If almost every purchase contains B, the rule may add little information.

Support, confidence, and lift describe different aspects of an association. Their interpretation matters as much as their calculation. A promising rule should also be checked on other transactions, including cases where it weakens or disappears. Even a repeatable association does not show that promoting one product would cause sales of another.

### Extract structure from text

Documents vary in length, vocabulary, and detail. Word-based methods provide a transparent starting point for finding related documents and exploring themes. Learned embeddings add a way to compare meaning beyond exact word overlap.

This is a direct application of representation learning. Two descriptions can use different words for a similar idea, while two nearly identical sentences can differ because of a negation. Embeddings may help with the first case and still fail on the second. Exact identifiers can also favor lexical search. Comparing results on the same questions, with explicit relevance judgments, makes these strengths and limitations visible.

### Study relationships through graphs

A graph represents objects as nodes and relationships as edges. Communication, citations, purchases, and constructed similarity links give different meanings to those edges. Two documents being similar is not the same observation as one document citing another.

Graph mining examines important nodes, groups of connected objects, and possible missing relationships. “Important” depends on the question: a node with many connections need not be the node connecting otherwise separate groups. Communities also depend on modeling choices and method settings. Comparing graph structure with text or attributes provides additional evidence for interpreting a result.

### Investigate unusual cases and practical limits

Anomaly detection identifies observations that differ enough from an expected pattern to deserve attention. The result depends on the features, the comparison population, and the number of cases that can realistically be reviewed. A large invoice could be an error or a wholesale order. A detector can prioritize inspection without settling that explanation.

As datasets grow, computation becomes another part of the decision. Approximate similarity search can reduce the work needed to find neighbors, but its results should be compared with an exact baseline. Reproducing exact neighbors and finding useful results are separate evaluation questions. Runtime, memory, and interpretation all contribute to whether a method is suitable.

### Bring the evidence together

The final part connects the methods through their conclusions. A useful analysis states its question, explains its representation and method, presents evidence, and identifies important limitations. Challenging a finding with another sample, threshold, or representation can reveal which parts are dependable and which need further investigation.

A result does not have to confirm the initial expectation to be useful. Discovering that a rule is fragile, a cluster is driven by scaling, or a simpler retrieval method works better can improve a decision. Knowing when the evidence is insufficient is also an outcome of a successful investigation.

## A recurring way of working

Across the course, the same reasoning appears in different forms: understand the records, choose a representation, discover a pattern, inspect examples, test a reasonable alternative, and explain what remains supported.

The notebooks combine self-contained explanations with runnable examples and independent experiments. Working code provides a starting point so attention can go to choices and interpretation. Predictions made before a change help distinguish learning from explaining any result after the fact. Hints and optional extensions support different levels of familiarity.

The course builds toward being able to explain an analysis to another person: what was observed, which assumptions shaped the result, what was checked, and what further evidence would change the conclusion. That is the connection between learning a representation and using it to discover knowledge.

Continue with [Week 1: Data Quality and Knowledge Discovery](../weeks/01/Week_01_Data_Quality_Knowledge_Discovery.ipynb).
