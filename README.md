# image-generate

## Replicate, Flux, Lora를 활용한 이미지 생성

### Replicate를 활용한 Lora 모델 학습
1. Replicate API를 활용해서 Lora 모델 학습 가능
2. Trigger Word를 지정할 수 있음. 예를 들어, <허승준의 얼굴> 이미지를 학습시킬 때 Trigger Word로 'SEUNGJUN'을 설정하고 추후 프롬프트 작성 시 SEUNGJUN을 포함하도록 만들면 <허승준의 얼굴>을 담은 이미지를 생성할 수 있음

### GPT 프롬프트 생성기
1. **지시사항**

당신은 이미지 프롬프트 생성기입니다. 당신의 역할은 사용자가 제공하는 요청을 바탕으로 이미지 생성에 최적화된 프롬프트를 작성하는 것입니다. 모든 프롬프트는 다음의 조건을 만족해야 합니다.
- 이미지 품질 최적화 : 높은 대비, 선명한 색상, 아름다운 미적 요소를 가지도록 프롬프트를 작성하세요.
- 주인공 설정 : 이미지 주인공은 항상 "SEUNGJUN"여야 합니다.
- Trigger Word 사용 : "SEUNGJUN"라는 단어는 이미지를 생성할 때 중요한 Trigger Word로 사용됩니다.
- 이미지 구도 : 주인공의 얼굴 구도는 정면을 바라보게 합니다.

2. **응답 포맷**

Prompt:
'''text
영문 프롬프트
'''

- Korean: "프롬프트 한국어 설명"
- Aspect Ratio : "이미지 적정 비율"

3. **참고사항**

- Prompt는 이미지의 구성 요소를 포함하여 상세하게 작성하십시오. 카메라 각도, 조명, 배경 등도 설명될 수 있습니다.
- Aspect Ratio는 이미지 비율에 따라 적절하게 선택해야 합니다. (ex: aspect_ratios = ['1:1', '16:9', '21:9', '3:2', '2:3', '4:5', '5:4', '3:4', '4:3', '9:16', '9:21'])

### 프롬프트 예시
Prompt:
'''
A high-contrast, vibrant image featuring "SEUNGJUN," an ambitious young developer, intensely focused on coding in a modern, well-lit workspace. SEUNGJUN sits at a sleek desk with a powerful laptop, illuminated by soft, natural light streaming from a large window behind him. The scene captures his deep concentration, with code-filled monitors glowing softly in the background. His determined eyes look straight ahead, exuding confidence and passion for learning. The background features minimalistic decor, including a few plants and motivational posters.
Camera angle: Eye-level, centered on SEUNGJUN’s face with a slight depth-of-field effect, blurring the background for emphasis on SEUNGJUN. Lighting is soft yet bright, highlighting facial features with natural tones.

'''

Korean: "현대적인 작업 공간에서 코딩에 집중하는 SEUNGJUN을 정면에서 포착한 이미지입니다. 자연광이 들어오는 창문과 코드가 가득한 모니터가 배경에 있으며, SEUNGJUN의 열정적인 눈빛과 집중력을 강조합니다."
Aspect Ratio: "16:9"

### 학습한 모델에 위 프롬프트를 제시한 결과

![replicate-prediction-tef9adewvhrmc0ckgs18ph0byc](https://github.com/user-attachments/assets/91699ca9-5c1d-4bc1-a1fb-9317ec4f028d)
