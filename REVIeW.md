# Paraphrasing for LLM

## [Paraphrase then run task](src/paraphrase_and_run_tasks.py)

HF TGI
HuggingFace TGI Server.

use_tgi = False # LLMs not trained for instructions
use_tgi_chat = True # LLMs trained for instructions

[tasks](src/paraphrase_and_run_tasks.py:481): each task was stored as a file whose link is in data/sample_tasks.txt

### HFTGIChat

### llms

[ llms ](src/paraphrase_and_run_tasks.py:535): a dict of llm models. Each model is a `HFTGIChat`

### [def run_tasks_for_llms()](src/paraphrase_and_run_tasks.py:447)

- generate a prompt by [PromptTemplate]

### [def run_tasks()](src/paraphrase_and_run_tasks.py:371) with LLMChain

- first run once to get the [result](src/paraphrase_and_run_tasks.py:397)
- then [paraphrase_prompt](src/paraphrase_and_run_tasks.py:422) with `original_instruction` and `paraphrase_type` which is the deepest element at [GROUPED_TYPES](src/paraphrase_and_run_tasks.py:37)
