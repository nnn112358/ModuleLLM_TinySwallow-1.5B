# ModuleLLM_TinySwallow-1.5B




```bash
userPC$  git clone https://github.com/AXERA-TECH/ax-llm-build.git
Cloning into 'ax-llm-build'...
remote: Enumerating objects: 51, done.
remote: Counting objects: 100% (51/51), done.
remote: Compressing objects: 100% (42/42), done.
remote: Total 51 (delta 28), reused 15 (delta 8), pack-reused 0 (from 0)
Receiving objects: 100% (51/51), 33.69 KiB | 1.02 MiB/s, done.
Resolving deltas: 100% (28/28), done.
```

```bash
userPC$ mkdir -p TinySwallow-1.5B-Instruct
userPC$ huggingface-cli download --resume-download SakanaAI/TinySwallow-1.5B-Instruct --local-dir TinySwallow-1.5B-Instruct
```

```
userPC$ sudo docker run -it --net host -v $PWD:/data pulsar2:3.3
```

```
root# pulsar2 llm_build --input_path TinySwallow-1.5B-Instruct --output_path TinySwallow-1.5B-Instruct-AX620E --kv_cache_len 1023 --hidden_state_type bf16 --prefill_len 128 --chip AX620E
<frozen quant.ppq.quantization.analyse.graphwise>:110: FutureWarning: Decorating classes is deprecated and will be disabled in future versions. You should only decorate functions or methods. To preserve the current behavior of class decoration, you can directly decorate the `__init__` method and nothing else.
Config(
    model_name='/gs/bs/tgi-24IBB/mkshing/models/smol-swallow/v3/step-310k',
    model_type='qwen2',
    num_hidden_layers=28,
    num_attention_heads=12,
    num_key_value_heads=2,
    hidden_size=1536,
    head_dim=0,
    intermediate_size=8960,
    vocab_size=151936,
    rope_theta=1000000.0,
    max_position_embeddings=32768,
    rope_partial_factor=1.0,
    rms_norm_eps=1e-06,
    norm_type='rms_norm',
    hidden_act='silu',
    hidden_act_param=0.03,
    scale_depth=1.4,
    scale_emb=1,
    dim_model_base=256,
    origin_model_type=''
)
2025-02-12 17:55:55.091 | SUCCESS  | yamain.command.llm_build:llm_build:123 - prepare llm model done!
building llm decode layers ⠙ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  0/28 0:00:562025-02-12 17:56:52.024 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠇ ━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  1/28 0:02:492025-02-12 17:58:44.636 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠇ ━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  2/28 0:04:492025-02-12 18:00:44.607 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠦ ━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  3/28 0:06:512025-02-12 18:02:46.896 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠼ ━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  4/28 0:08:582025-02-12 18:04:53.931 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠴ ━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  5/28 0:11:022025-02-12 18:06:58.024 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠼ ━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  6/28 0:13:012025-02-12 18:08:56.269 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠙ ━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  7/28 0:14:542025-02-12 18:10:49.626 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠹ ━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  8/28 0:17:082025-02-12 18:13:03.301 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠧ ━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  9/28 0:19:122025-02-12 18:15:07.785 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠸ ━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 10/28 0:21:102025-02-12 18:17:05.820 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠸ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 11/28 0:23:142025-02-12 18:19:09.765 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠹ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12/28 0:25:202025-02-12 18:21:15.371 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠇ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 13/28 0:27:212025-02-12 18:23:16.673 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠼ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 14/28 0:29:212025-02-12 18:25:17.131 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠸ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 15/28 0:31:222025-02-12 18:27:17.864 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠙ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 16/28 0:33:362025-02-12 18:29:31.331 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠹ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 17/28 0:35:422025-02-12 18:31:37.794 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠼ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━━━━━━━━━ 18/28 0:37:432025-02-12 18:33:38.721 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠸ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━━━━ 19/28 0:39:442025-02-12 18:35:39.419 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠴ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━━━━━━━━━ 20/28 0:41:422025-02-12 18:37:38.013 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠦ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━━━━ 21/28 0:43:522025-02-12 18:39:47.653 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠦ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━━━━━━━━━ 22/28 0:45:522025-02-12 18:41:47.632 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠇ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━━━━ 23/28 0:47:472025-02-12 18:43:42.287 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠸ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━━━━━━━━━ 24/28 0:49:362025-02-12 18:45:31.404 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠏ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━━━━ 25/28 0:51:282025-02-12 18:47:23.872 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠇ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╸━━━━━ 26/28 0:53:222025-02-12 18:49:17.387 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers ⠹ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╺━━ 27/28 0:55:512025-02-12 18:51:46.536 | WARNING  | yasched.test_onepass:remove_useless_job:2737 - 8 redundant metajobs are filtered out!
building llm decode layers   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 28/28 0:56:44
building llm post layer   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1/1 0:04:55
2025-02-12 18:57:35.194 | SUCCESS  | yamain.command.llm_build:llm_build:199 - build llm model done!
2025-02-12 18:59:43.463 | SUCCESS  | yamain.command.llm_build:llm_build:380 - check llm model done!
```

```
root@Thinkpad-T14:/data# chmod +x ./tools/fp32_to_bf16
root@Thinkpad-T14:/data# chmod +x ./tools/embed_process.sh
```


