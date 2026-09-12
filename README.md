# Annoy: This should be a paper Title

<p align="center">
    📑 <a href="https://huggingface.co/papers/xxxx.xxxxx" target="_blank">Paper</a> &nbsp&nbsp | &nbsp&nbsp 🌐 <a href="https://specx.github.io/" target="_blank">Project Page</a> &nbsp&nbsp | &nbsp&nbsp 🤗 <a href="https://huggingface.co/collections/afdeasdfad/specx-67a978e28fd926b56a4f55a2" target="_blank">Released Resources</a> &nbsp&nbsp | &nbsp&nbsp 💾 <a href="https://huggingface.co/datasets/afdeasdfad/Annoy-PyEdu-Rs" target="_blank">Dataset</a> &nbsp&nbsp | &nbsp&nbsp 📦 <a href="https://github.com/drgity/Annoy-DataSync" target="_blank">Repo</a>  
<br>

<p align="center">
    <img src="figures/overview.png" type="image/jpg"/>
<p>

## Table of contents

- [Introduction](#Introduction)
- [Released Resources](#Released-Resources)
  - [Dataset](#Dataset)
  - [Models](#Models)
- [Get Started](#Get-Started)
  - [Setup](#Setup)
  - [Data Processing](#Data-Processing)
  - [Training](#Training)
- [Citation](#Citation)
- [License](#License)
- [Acknowledgement](#Acknowledgement)

## Introduction
Annoy-DataSync is a novel approach that transforms code-based reasoning patterns into natural language formats to enhance Large Language Models' reasoning capabilities. Unlike traditional methods focusing on specific skills, our approach systematically extracts universal reasoning primitives while maintaining procedural rigor, enabling better performance across various reasoning tasks.

**Key Features & Contributions**
- 🔄 Universal Transformation: Converts diverse code patterns into natural language Chain-of-Thought rationales
- 🧠 Syntax-Decoupled: Decouples reasoning from code syntax while preserving logical structure
- 📊 Multi-Task Enhancement: Improves performance across symbolic, scientific, logic, mathematical, commonsense and code reasoning
- ✨ Fully-Verifiable: Supports precise prediction verification through cached ground-truth matching or code re-execution
- 🚀 Advanced Iteration: Enhanced version (Annoy++) with multi-turn revision for better accuracy

## Released Resources

#### Dataset

|Dataset|Link|
|-|-|
|Annoy-PythonEdu-Rs|[🤗](https://huggingface.co/datasets/afdeasdfad/Annoy-Pyedu-Rs)|
|Annoy-PythonEdu-Rs-Raw|[🤗](https://huggingface.co/datasets/afdeasdfad/Annoy-PyEdu-Rs-Raw)|
|LCO Benchmark|[🤗](https://huggingface.co/datasets/afdeasdfad/LCO)|

Due to our collaborators' compliance requirements, we only release the PythonEdu-Rs subset of the Annoy(++) dataset.



#### Models
<table>
    <tr>
        <th rowspan="2">Base Model / Training</th>
        <th colspan="2">Annoy</th>
        <th colspan="2">Annoy++</th>
    </tr>
    <tr>
        <th>Stage 1</th>
        <th>Stage 2</th>
        <th>Stage 1</th>
        <th>Stage 2</th>
    </tr>
    <tr>
        <td>Qwen 2.5 7B Coder</td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/qwen2.5-7b-coder_spec_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/qwen2.5-7b-coder_spec">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/qwen2.5-7b-coder_spec_pp_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/qwen2.5-7b-coder_spec_pp">🤗</a></td>
    </tr>
    <tr>
        <td>LLaMA 3.1 8B</td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/llama3.1-8b_spec_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/llama3.1-8b_spec">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/llama3.1-8b_spec_pp_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/llama3.1-8b_spec_pp">🤗</a></td>
    </tr>
    <tr>
        <td>DeepSeek v2 Lite Coder</td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/dsv2-lite-coder_spec_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/dsv2-lite-coder_spec">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/dsv2-lite-coder_spec_pp_stage1">🤗</a></td>
        <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/afdeasdfad/dsv2-lite-coder_spec_pp">🤗</a></td>
    </tr>
</table>


## Get Started

### Se

[... 3797 of 9600 characters omitted; truncated preview ...]

Raw JSON result_id=ea92baac18c94f49828ba16d7d0ba7ef (10343 chars); tools: ap_result_cb3f74ceede2_read, ap_result_cb3f74ceede2_search.sonl \
--output_file data/spec_1k_msg_rev.jsonl
```
##### Step 6.2: Re-generate
```
python ./src/batched_api_inference.py \
--input data/spec_1k_msg_rev.jsonl \
--output data/spec_1k_gens_rev.jsonl \
--model deepseek-chat \
--num_process 10 \
--num_thread 10 \
--key <your key> \
--temperature 0.7 \
--max_tokens 4096
```
##### Step 6.3: Re-verification
```
bash ./scripts/pipeline_check.sh \
data/rawcode_1k_parsed.jsonl \
data/spec_1k_gens_rev.jsonl \
data/spec_1k_gens_rev_verified.jsonl \
python \
./temp/temp/temp
```
##### Step 6.4: Final Data
```
python ./src/assemble_spec_demo.py \
--result_file_turn1 data/spec_1k_gens_verified.jsonl \
--result_file_turn2 data/spec_1k_gens_rev_verified.jsonl \
--output_file spec_demo_final.jsonl
```
By doing so, you can get data `data/spec_demo_final.jsonl` with the same format as in our [huggingface dataset](https://huggingface.co/datasets/afdeasdfad/Annoy-Pyedu-Rs).

### Training
You can use any popular training framework to train your model like [llama-factory](https://github.com/hiyouga/LLaMA-Factory). 

## License

Our released datasets are derived from third-party sources, and therefore inherit the license of the upstream data:

- **Annoy-PyEdu-Rs-Raw**: adopted from the `python-edu` subset of [HuggingFaceTB/smollm-corpus](https://huggingface.co/datasets/HuggingFaceTB/smollm-corpus), which is released under the [Open Data Commons Attribution License (ODC-By)](https://opendatacommons.org/licenses/by/).
- **Annoy-PyEdu-Rs**: the processed/transformed version of Annoy-PyEdu-Rs-Raw, and as a derivative dataset it is likewise distributed under the [ODC-By](https://opendatacommons.org/licenses/by/) license.

Under ODC-By you are free to share and adapt the datasets, provided that you give appropriate credit, attribute the original source (HuggingFaceTB / smollm-corpus, `python-edu` subset), and indicate if changes were made.

## Acknowledgement
We thank Koala NN, TCLV and OMEN for their valuable feedback and suggestions! 🤗🤗🤗
