## KoreanASR-ESPnet
`recog_wav2.sh` 는 학습이 끝난 모델을 새로운 단일 입력을 이용하여 predict 하는 코드입니다.

> `~/espnet/utils/recog_wav.sh` 를 일부 수정하였습니다.

자체적으로 제공하는 모델이 아닌 사용자가 만든 모델을 이용하여 단일 입력된 wav파일을 predict 합니다.

## Predict (Decoding)
`recog_wav.sh` 는 터미널에서 예측하고 싶은 wav 파일의 경로를 입력하여 해당 음성의 발화를 예측하여 표시합니다.

* Ksponspeech 데이터를 이용한 한국어 ASR 모델의 예측으로 사용하였습니다.

lang-model 은 사용하지 않고 recog-model 만 사용하여 decoding 하였습니다.
gpu를 사용하지 않으며, 5초정도의 wav파일의 decoding에 약 30초 가량 소요됩니다.



### How to use
학습이 끝난 사용자 지정 모델을 사용하여 단일 입력된 wav파일을 predict 합니다.
```
#Decode using model file

$0 --cmvn cmvn.ark --recog_model model.acc.best --decode_config conf/decode.yaml example.wav
```



**ex)** `run.sh`가 있는 asr1 디렉토리에서 실행할 경우

```
bash ../../../utils/recog_wav2.sh --cmvn cmvn.ark --recog_model model.acc.best --decode_config conf/decode.yaml example.wav
```
- `--cmvn`, `--recog_model`, `--decode_config` 뒤에는 해당 모델이 저장된 디렉토리 안의 `cmvn.ark`, `model.acc.best`, `decode.yaml` 파일의 경로를 작성합니다.
- `example.wav` 또한 decoding 하려는 wav파일의 경로를 포함합니다.
