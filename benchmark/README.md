# Benchmark

We provide several profiling tools to benchmark our models.

## profile with dataset

Download the dataset below or create your own dataset.

```bash
wget https://huggingface.co/datasets/anon8231489123/ShareGPT_Vicuna_unfiltered/resolve/main/ShareGPT_V3_unfiltered_cleaned_split.json
```

Profiling your model with `profile_throughput.py`

```bash
python profile_throughput.py \
 ShareGPT_V3_unfiltered_cleaned_split.json \
 /path/to/your/model \
 --concurrency 64
```

## profile without dataset

`profile_generation.py` perform benchmark with dummy data.

```shell
pip install nvidia-ml-py
```

```bash
python profile_generation.py \
 /path/to/your/model \
 --concurrency 1 8 --prompt-tokens 1 512 --completion-tokens 2048 512
```

## profile restful api

`profile_restful_api.py` is used to do benchmark on api server.

```bash
wget https://huggingface.co/datasets/anon8231489123/ShareGPT_Vicuna_unfiltered/resolve/main/ShareGPT_V3_unfiltered_cleaned_split.json

python3 profile_restful_api.py --backend lmdeploy --dataset-path ./ShareGPT_V3_unfiltered_cleaned_split.json
```
