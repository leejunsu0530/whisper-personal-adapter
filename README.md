# whisper-personal-adapter
특정인물 대상으로 학습된 whisper-turbo/kotoba-whisper

## 데이터셋 준비
1. 유튜브 영상 다운로드
2. 전처리(배경음 제거, VAD)
3. 오디오 발화 구간 잘라내기
4. 전사(AI 활용 및 수작업 결합)

## LoRA 튜닝
1. whisper-turbo와 kotoba-whisper에 대하여, encoder, decoder, encoder-decoder에 대해 파인튜닝
2. 벤치마크
3. 부족한 부분의 데이터 추가

## 실 활용
- ct2 기반 faster-whisper나 whisper.cpp로 변환하여 활용
- 양자화
- hf hub와 optimum
- nvidia gpu 활용
- openvino genai로 intel npu 활용

## 추가사항
- 라이선스 주의
