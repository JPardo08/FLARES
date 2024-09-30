# IberLEF 2024 - FLARES: Fine-Grained Language-based Reliability Detection in Spanish News

Welcome to the repository for **FLARES (Fine-Grained Language-based Reliability Detection in Spanish News)** submission by **Kfloeg Team**. This project focuses on evaluating the reliability of the language used in Spanish news articles by identifying and analyzing key information using the 5W1H method (Who, What, When, Where, Why, How). **K-Flares** is a K-Adapter-based approach designed for the **FLARES challenge**. The challenge consists of two subtasks:
  1. **Subtask 1**: Identification of 5W1H labels in textual data extracted from news articles.
  2. **Subtask 2**: Classifying the reliability of each 5W1H element.
K-Flares specifically addresses **Subtask 1** (5W1H identification).

## Repository Structure and Files
- **Paper**: `IberLEF24_KFlares.pdf`
  - This is the full paper submitted for the IberLEF, outlining the methodology, objectives, and key findings of the research.
  
- **Presentation**: `K-flares_definitiva2.pdf`
  - A slide deck summarizing the key points of the research, designed for a 10-minute oral presentation at the IberLEF.

- **Poster**: `FLARES_poster_definitivo.pdf`
  - A poster highlighting the main contributions and findings of the research, used for the IberLEF's poster session.

## Abstract
We refer as 5W1H method to the technique used to extract comprehensive information from textual data answering the questions Who, What, When, Where, Why, and How. Identifying these instances within a text can provide a structured approach to better understand the details presented in a text, which can help to assess the reliability of the information displayed there. In this context, we present K-Flares, an adaptation of the original work of K-Adapter for 5W1H Instances Recognition in the context of the challenge of FLARES 2024. In this challenge the aim is to detect 5W1H instances from text and assess the reliability of the information displayed in each of them. We focus on the first part of the task, the detection of 5W1H instances.


## Approach
- The approach uses two different **adapters** based on the Spanish version of **roBERTa** as the baseline language model.
  1. **5W1H Adapter**:  
     - Treats the task as a Named-Entity Recognition (NER) problem where 5W1H labels are the entities to be detected.
     - Generates **knowledge graphs** with the "WHAT" element as the core, relating it to other elements in the sample.
  2. **Wikidata Factual Adapter**:  
     - Uses the **mREBEL model** to generate triples from the text based on factual knowledge from **Wikidata**.
- We also used **prompt-engineering** to perform both tasks. 

## Key Findings
- Both adapters were used independently and in combination, with the **5W1H adapter** yielding the best results.
- The approach achieved a **65.95% accuracy** on the test set, winning the challenge.
- **Prompt-engineering** strategy didn't output good results.

## Results & Insights
- **Inter-label interactions**: The inclusion of knowledge about how the **5W1H labels** interact improved the learning process in the NER task.
- **External knowledge graphs**: The inclusion of factual knowledge from external sources like **Wikidata** slightly decreased model performance.
- The approach demonstrates that treating the problem as an NER task, combined with external knowledge, is both feasible and effective for this challenge.

## Team
Ontology Engineering Group, Departamento de Inteligencia Artificial, Departamento de Sistemas Informáticos, ETSI Informáticos, Universidad Politécnica de Madrid, Madrid, Spain.
- Joel Pardo-Ferrera
- Jiayun Liu
- Virginia Ramón-Ferrer
- Elvira Amador-Domínguez
- Pablo Calleja-Ibáñez

## Funding
This work has been funded by INESData (Infraestructura para la INvestigación de ESpacios de DAtos distribuidos en UPM) project, from Ministerio para la Transformación Digital y de la Función Pública (PRTR, UNICO I+D CLOUD, EU NextGeneration).


## Installation
If you'd like to explore the paper and materials, simply clone the repository:

```bash
git clone https://github.com/JPardo08/FLARES.git
