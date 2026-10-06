# whisper-personal-adapter
특정인물 대상으로 학습된 whisper-turbo/kotoba-whisper

## Goal
- 한 명의 특정 인물 뿐만 아니라, 원하는 인물의 데이터만 있다면 모델의 어뎁터를 만들 수 있는 시스템 구축
- 구어체, 게임 상황 등에 대응되는 특화 어뎁터 구축 시스템
- (불확실) community correction feedback system 구축

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
- **데이터셋 없이** 모델과, 데이터셋을 넣었을 때의 학습 코드만을 공개하고 여러 대상에 대한 community correction 시스템 구축. 
    - 시스템 개요: 영상 url, 타임스템프, 오답/정답 전사 문장. 이용자측에서 이에 대한 추가 피드백을 대댓글의 형식으로 제공 가능
    - 이 시스템에서 충분히 피드백한 모델을 그 다음 버전으로 배포. 
    - 다만 혼자 관리하기에 업무량이 많을 수 있고, 과적합의 위험이 있음.

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