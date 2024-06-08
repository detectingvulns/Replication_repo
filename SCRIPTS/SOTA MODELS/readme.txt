The sota_models.zip can be downloaded from:
https://drive.google.com/file/d/1fxf3lzktAxP0xq3nmReYH8il4-qXxJQa/view?usp=sharing


VulCurator and MemVul are loaded in the docker image.
detectingvulns/sota_models

* VulCurator
** Use the docker container: detectingvulns/sota_models and navigate to the /VFDetector
** Replace the cves.json file with your input and rename it back to cves.json
** Run the shell_commands.sh 
** Result is in output.json
** All the above steps are automated also via these two scripts (automate_at_docker_container.sh and automate_at_local.sh). 

* MemVul
** Use the docker container: detectingvulns/sota_models and navigate to the /MemVul 
** Replace the /MemVul/Data/data/test_project.json file with the input created by you. Rename it to test_project.json
** Execute the following commands:
*** source ./env/bin/activate
*** python predict_memory.py
** The output is at /MemVul/Data/test_results/out_memvul_result.json


The LineVul model implementation is provided in the ./LineVul/linevul_model/
** The file exec_linevul_main.py is the entry point. Running this would yield the output as result_output.csv.
** The command to run is:
*** python exec_linevul_main.py \
  --model_name=model_python.bin \
  --output_dir=./saved_models \
  --model_type=roberta \
  --tokenizer_name=microsoft/codebert-base \
  --model_name_or_path=microsoft/codebert-base \
  --do_test \
  --test_data_file=../data/test_py_feb.csv \
  --block_size 512 \
  --eval_batch_size 512
*** Replace the input and model name appropriately. 




