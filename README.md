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

## 참고 프로젝트
- [jp-jitsumu lora](https://huggingface.co/tokimoa/jp-jitsumu-whisper-lora)
- [위 프로젝트의 후계. turbo ft](https://huggingface.co/tokimoa/jp-jitsumu-whisper-turbo-lora)
- [hf hub의 whisper-base 리포](https://huggingface.co/openai/whisper-base)
- [whisper lore tuning](https://medium.com/@anitaliubfsu/fine-tuning-whisper-with-lora-c796781f00f5)
- [데이터 없이 양자화](https://huggingface.co/docs/optimum-intel/en/openvino/optimization)

### intel npu
- [2026 npu whisper](https://docs.openvino.ai/2026/openvino-workflow-generative/inference-with-genai/inference-with-genai-on-npu.html?utm_source=chatgpt.com#whisper-inference-on-npu)
- [메모리 벤치마크](https://wewegh.tistory.com/93)
- [음성인식 범용](https://openvinotoolkit.github.io/openvino.genai/docs/use-cases/speech-recognition/)
- [깃허브](https://github.com/openvinotoolkit/openvino.genai)
- [~서버용 단어수준 타임스템프 export~](https://docs.openvino.ai/2026/model-server/ovms_demos_audio.html?utm_source=chatgpt.com)