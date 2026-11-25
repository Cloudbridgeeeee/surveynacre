# SurveyNacre — proposed AWS architecture

SurveyNacre uses AWS to analyse large volumes of free text quickly, keep every finding linked to evidence and protect respondent anonymity.

## Request flow

1. Survey CSV
2. Amazon S3
3. AWS Lambda
4. Bedrock
5. Comprehend
6. OpenSearch
7. Researcher review

## Services

### Amazon Bedrock

**Role:** Classify, cluster and summarise

Classifies responses into codeframes, clusters emerging themes and drafts evidence-linked findings that cite the responses they draw on.

### Amazon Comprehend

**Role:** Measure sentiment

Scores sentiment for each response and theme, including mixed sentiment, so researchers see how people feel about each topic.

### Amazon OpenSearch Service

**Role:** Find the quotes

Indexes responses with their codes and embeddings so researchers can search by meaning and pull representative quotes instantly.

### Amazon S3

**Role:** Store survey data

Keeps uploaded survey files encrypted and separated per project, with identifiers removed before analysis.

### AWS Lambda

**Role:** Orchestrate analysis

Runs de-identification, classification, sentiment scoring and indexing for each upload, and assembles report exports.

## Principles

- **Evidence or nothing** — Every finding links to supporting responses.
- **Respondents anonymous** — Identifiers are removed before analysis.
- **Researchers decide** — AI proposes codes; researchers confirm them.

## Safeguards

- **Researcher review** — Codes and findings are reviewed by researchers before reporting.
- **Evidence-linked** — Every theme and claim links to the responses behind it.
- **Anonymous by design** — Respondent identifiers are removed before analysis.
- **Method transparency** — Coverage, confidence and agreement are reported alongside findings.

## MVP scope

Bring a completed survey. We classify and theme its open-ended responses, your researchers review the coding, and you receive an evidence-linked report and dashboard.

- CSV upload and de-identification
- Classification and clustering
- Sentiment by theme
- Researcher review workspace
- Evidence-linked report
