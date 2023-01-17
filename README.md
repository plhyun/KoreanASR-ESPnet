# KoreanASR-ESPnet
학습이 끝난 모델을 새로운 단일 입력을 이용하여 predict 하는 코드입니다.
recog_wav.sh 는 터미널에서 예측하고 싶은 wav 파일의 경로를 입력하여 해당 음성의 발화를 예측하여 표시합니다.

Ksponspeech 데이터를 이용한 한국어ASR모델의 예측으로 사용하였습니다.

lang-model은 사용하지 않고 recog-model만 사용하여 decoding 하였습니다.

gpu를 사용하지 않으며, 5초정도의 wav파일의 decoding에 약 30초 가량 소요됩니다.
