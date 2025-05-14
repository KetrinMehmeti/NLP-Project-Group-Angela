# Introduction
 
The PubMedQA dataset is an innovative resource for question answering (QA) in the biomedical field, created from abstracts of scientific articles available on PubMed. The main purpose of PubMedQA is to assess the reasoning and inference abilities of intelligent systems on natural language, particularly within the context of biomedical research texts, which often require the processing of quantitative content.

A typical instance in PubMedQA consists of the following components:

* A question, which can either be the original title of a research paper or derived from it. For example: "Do preoperative statins reduce atrial fibrillation after coronary artery bypass grafting?"
* A context, which is the abstract corresponding to the question, excluding its conclusion.
* A long answer, represented by the conclusion of the abstract, which is expected to answer the research question.
* A short answer in the form of "yes," "no," or "maybe," summarizing the conclusion. In the provided example, the long answer is: "(Conclusion) Our study indicated that preoperative statin therapy seems to reduce AF development after CABG," while the short answer is "yes."

The PubMedQA dataset is divided into three subsets:

* PQA-L (Labeled): Contains 1k manually annotated instances with yes/no/maybe answers. These annotations were made in two modes: "reasoning-free," where the annotator had access to the long answer, and "reasoning-required," where the annotator could only rely on the context.
* PQA-U (Unlabeled): Consists of 61.2k unlabeled instances, made up of PubMed articles with question-form titles and structured abstracts.
* PQA-A (Artificial): Includes 211.3k artificially generated instances, where article titles in statement form are converted into questions, and yes/no answers are automatically assigned based on the presence or absence of negations in the original title.

A key feature of PubMedQA is that the contexts are generated to directly answer the questions, with both components written by the same authors, ensuring a strong relationship between the question and context. This makes PubMedQA an ideal benchmark for testing the scientific reasoning capabilities of machine reading comprehension models. The dataset often requires reasoning over the quantitative content found in abstracts to answer the questions.

## Description of the Expert-Annotated PQA-L Dataset

PQA-L is a key subset of the PubMedQA dataset, consisting of 1,000 manually labeled QA instances created for validation and testing. Each instance includes a question (usually a paper title), context (the abstract without the conclusion), a long answer (the conclusion), and a short yes/no/maybe label.

Two M.D. candidates annotated the data using two setups:

* Reasoning-free: the annotator saw the question, context, and long answer to assign the label directly.
* Reanoning-required: the annotator only saw the question and context, requiring inference without the conclusion.

Final labels were based on agreement between annotators, with disagreements resolved through discussion or instance removal. This dual-setup design highlights the task's difficulty: human accuracy drops from 90.4% (reasoning-free) to 78.0% (reasoning-required). The labels reflect the certainty or ambiguity of the article’s conclusion.


# Pipeline 
1. Preliminary analysis:
Briefly describe the data:
    - What is the structure of the dataset? What type of task was the dataset collected for?
    - What type of documents does it contain? How many are there? How long are they on average and
    what is their distribution?
    - How big is the vocabulary of the collection? How big is the vocabulary of a document on average?
    Play around with documents using code from the early parts of the course. For example, you could:
    - Cluster the documents, visualise the clusters and to try to understand what types of groups are
    present.
    - Index the documents so that you can perform keyword search over them.
    - Train a Word2Vec embedding and investigate the properties of the resulting embedding.

2. Training models:
Each dataset has been created with a particular task in mind. You don’t necessarily need to tackle that
particular problem, but you do need to train some model(s) on the data:
    - train ML models (e.g. a linear classifier, an LSTM and/or a Transformer) to perform a particular
    task on the data;
    - if possible, try to fine-tune a pretrained models on the same task and compare their performance;
    - try an LLM on the task, comparing one, few and zero-shot performance;
    - and perhaps even try to fine-tune a small LLM on the task (if it makes sense to do so).

3. Possible extensions:
Depending on the dataset chosen there will be many additional investigations that you could perform,
for example:
    • investigate another task on the same dataset,
    • investigate the same task on a related dataset,
    • use text-to-speech and speech-to-text models to create a voice interactive chatbot,
    • create your own dialog dataset by transcribing audio conversations (e.g. using MS Teams).