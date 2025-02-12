# ModuleLLM_TinySwallow-1.5B

## Result

https://x.com/nnn112358/status/1889658632536559726

## Model Convert

このログは、TinySwallow-1.5Bモデルを AX620E チップ向けに最適化・変換する過程を示しています。

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
Hugging Faceからモデルをダウンロード。
Docker環境の起動:

```
userPC$ sudo docker run -it --net host -v $PWD:/data pulsar2:3.3
```

```
root# pulsar2 llm_build --input_path TinySwallow-1.5B-Instruct --output_path TinySwallow-1.5B-Instruct-AX620E --kv_cache_len 1023 --hidden_state_type bf16 --prefill_len 128 --chip AX620E
```
主なパラメータ:
 * --kv_cache_len 1023: KVキャッシュの長さを1023に設定
 * --hidden_state_type bf16: 隠れ状態をbf16形式で量子化
 * --prefill_len 128: プレフィル長を128に設定
 * --chip AX620E: ターゲットチップをAX620Eに指定

```
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
モデルは28層のデコーダーレイヤーを持っており、各層の変換に約2分かかっています
全体の変換プロセスは約1時間（56分44秒）かかりました

* 隠れ層サイズ: 1536
* アテンションヘッド数: 12
* KVヘッド数: 2
* 中間層サイズ: 8960
* 語彙サイズ: 151936

```
root@Thinkpad-T14:/data# chmod +x ./tools/fp32_to_bf16
root@Thinkpad-T14:/data# chmod +x ./tools/embed_process.sh
```

## Module-LLMにコピーします。

```
root@Thinkpad-T14:/data# tree ./TinySwallow
├── TinySwallow-1.5B-Instruct-AX620E    #Pulsar2で変換したものです。
│   ├── model.embed_tokens.weight.bfloat16.bin
│   ├── model.embed_tokens.weight.float32.bin
│   ├── model.embed_tokens.weight.npy
│   ├── qwen2_p128_l0_together.axmodel
│   ├── qwen2_p128_l10_together.axmodel
│   ├── qwen2_p128_l11_together.axmodel
│   ├── qwen2_p128_l12_together.axmodel
│   ├── qwen2_p128_l13_together.axmodel
│   ├── qwen2_p128_l14_together.axmodel
│   ├── qwen2_p128_l15_together.axmodel
│   ├── qwen2_p128_l16_together.axmodel
│   ├── qwen2_p128_l17_together.axmodel
│   ├── qwen2_p128_l18_together.axmodel
│   ├── qwen2_p128_l19_together.axmodel
│   ├── qwen2_p128_l1_together.axmodel
│   ├── qwen2_p128_l20_together.axmodel
│   ├── qwen2_p128_l21_together.axmodel
│   ├── qwen2_p128_l22_together.axmodel
│   ├── qwen2_p128_l23_together.axmodel
│   ├── qwen2_p128_l24_together.axmodel
│   ├── qwen2_p128_l25_together.axmodel
│   ├── qwen2_p128_l26_together.axmodel
│   ├── qwen2_p128_l27_together.axmodel
│   ├── qwen2_p128_l2_together.axmodel
│   ├── qwen2_p128_l3_together.axmodel
│   ├── qwen2_p128_l4_together.axmodel
│   ├── qwen2_p128_l5_together.axmodel
│   ├── qwen2_p128_l6_together.axmodel
│   ├── qwen2_p128_l7_together.axmodel
│   ├── qwen2_p128_l8_together.axmodel
│   ├── qwen2_p128_l9_together.axmodel
│   └── qwen2_post.axmodel
├── main_prefill
├── run_tinyswallow_1.5B_ax630c.sh
├── tinyswallow_tokenizer        #tinyswallowのjsonファイルです
│   ├── added_tokens.json
│   ├── config.json
│   ├── generation_config.json
│   ├── special_tokens_map.json
│   ├── tokenizer.json
│   ├── tokenizer_config.json
│   └── vocab.json
└── tinyswallow_tokenizer.py
```

## run_tinyswallow_1.5B_ax630c.shの編集
```run_tinyswallow_1.5B_ax630c.sh
./main_prefill \
--template_filename_axmodel "TinySwallow-1.5B-Instruct-AX620E/qwen2_p128_l%d_together.axmodel" \    ##フォルダ名の変更
--axmodel_num 28 \    #axmodelの数にあわせて変更
--tokenizer_type 2 \    
--filename_tokenizer_model "http://localhost:8080" \        # tinyswallow_tokenizer.pyのポート番号にあわせる
--bos 0 --eos 0 \
--filename_post_axmodel "TinySwallow-1.5B-Instruct-AX620E/qwen2_post.axmodel" \    ##フォルダ名の変更
--filename_tokens_embed "TinySwallow-1.5B-Instruct-AX620E/model.embed_tokens.weight.bfloat16.bin" \    #フォルダ名の変更
--tokens_embed_num 151936 \    #Pulsar2 llmbuild起動時 Config->vocab_size=151936
--tokens_embed_size 1536 \    #Pulsar2 llmbuild起動時 Config->hidden_size=1536
--use_mmap_load_embed 1 \
--live_print 1 \
--continue 1 \
--prompt "$1"
```


# Reference

* Pulsar2:4. Large Model Compilation (Experimental Stage)<br>
https://pulsar2-docs.readthedocs.io/en/latest/<br>

* M5Stack Module LLMでFunction Callingを実行<br>
https://qiita.com/motoh_qiita/items/1b0882e507e803982753<br>

 * SakanaAI/TinySwallow-1.5B-Instruct<br>
https://huggingface.co/SakanaAI/TinySwallow-1.5B-Instruct<br>

 * 新手法「TAID」を用いた小規模日本語言語モデル「TinySwallow-1.5B」の公開<br>
https://sakana.ai/taid-jp/<br>
