### Conformer-LAS + SpecAugment (no LM), hierarchical subsample1/8
- conf: `conf/asr/conformer_kernel15_clamp10_hie_subsample8_las_ln.yaml`
- decoding parameters
  - epoch: 60
  - n_average: 10
  - beam width: 10
  - lm_weight: 0.0

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|96.0|3.9|0.1|0.1|**4.1**|33.0|
|test|7176|104765|95.5|4.3|0.1|0.1|**4.5**|35.3|


### Transformer + SpecAugment (no LM), hierarchical subsample1/8
- conf: `conf/asr/transformer_dec_attn_typehie_subsample8.yaml`
- decoding parameters
  - epoch: 40
  - n_average: 10
  - beam width: 5
  - lm_weight: 0.0

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|95.1|4.8|0.1|0.1|**5.0**|35.9|
|test|7176|104765|94.6|5.2|0.2|0.1|**5.5**|38.3|


### Transformer + SpecAugment (no LM)
- conf: `conf/asr/transformer.yaml`
- decoding parameters
  - epoch: 35
  - n_average: 10
  - beam width: 5
  - lm_weight: 0.0

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|95.1|4.8|0.1|0.1|**5.0**|36.0|
|test|7176|104765|94.7|5.1|0.2|0.1|**5.4**|37.7|


### BLSTM-LAS
- conf: `conf/asr/blstm_las.yaml`
- lm_conf: `conf/lm/rnnlm.yaml`
- decoding parameters
  - beam width: 5
  - lm_weight: 0.3

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|94.6|5.2|0.1|0.1|**5.5**|38.9|
|test|7176|104765|93.9|5.9|0.2|0.1|**6.2**|42.3|


### Offline Transformer-MMA, hierarchical subsample1/8
- conf: `conf/asr/mma/transformer_mma_ma4H_ca4H_w16_from4L_subsample8.yaml`
- lm_conf: `conf/lm/rnnlm.yaml`
- decoding parameters
  - epoch: 25
  - n_average: 10
  - beam width: 10
  - lm_weight: 0.3
  - length_penalty: 2.0
  - mma_delay_threshold: 8

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|94.7|5.2|0.1|0.1|**5.4**|38.8|
|dev|7176|104765|94.2|5.6|0.2|0.1|**5.9**|40.7|


### Streaming Transformer-MMA, hierarchical subsample1/8, chunk-hop: 96/64/32
- conf: `conf/asr/mma/lc_transformer_mma_subsample8_ma4H_ca4H_w16_from4L_96_64_32.yaml`
- lm_conf: `conf/lm/rnnlm.yaml`
- decoding parameters
  - epoch: 25
  - n_average: 10
  - beam width: 10
  - lm_weight: 0.3
  - length_penalty: 2.0
  - mma_delay_threshold: 8

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|94.4|5.4|0.2|0.1|**5.7**|39.5|
|test|7176|104765|93.8|5.9|0.2|0.2|**6.3**|41.8|


### Streaming Transformer-MMA, hierarchical subsample1/8, chunk-hop: 64/128/64
- conf: `conf/asr/mma/lc_transformer_mma_subsample8_ma4H_ca4H_w16_from4L_64_128_64.yaml`
- lm_conf: `conf/lm/rnnlm.yaml`
- decoding parameters
  - epoch: 25
  - n_average: 10
  - beam width: 10
  - lm_weight: 0.3
  - length_penalty: 2.0
  - mma_delay_threshold: 8

| Eval Set | # Snt | # Wrd | Corr | Sub | Del | Ins | Err | S.Err |
| -------- | ----- | ----- | ---- | --- | --- | --- | --- | ----- |
|dev|14326|205341|94.7|5.2|0.1|0.1|**5.4**|38.8|
|test|7176|104765|94.1|5.7|0.2|0.2|**6.1**|41.4|
