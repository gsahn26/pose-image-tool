# 테스트에 쓴 프롬프트

- 모델: Realistic Vision V5.1 (SD 1.5 계열) + ControlNet v1.1 OpenPose + VAE sd-vae-ft-mse
- 시드: 42 / 스텝: 30
- 네거티브 프롬프트: `lowres, blurry, deformed face, distorted face, bad eyes, face mask, deformed hands, extra limbs, cartoon, 3d render`

| 결과 파일 | 포즈 | 프롬프트 |
|---|---|---|
| output_01.png | pose_01 | a factory worker in a white safety helmet and blue overalls, inside a bright manufacturing plant, detailed realistic face, natural skin, sharp eyes, photorealistic documentary photography |
| expA_01.png | pose_01 | an astronaut in a white space suit on the surface of the moon, photorealistic |
| expA_02.png | pose_01 | a chef in a white uniform in a busy restaurant kitchen, warm lighting, photorealistic |
| expA_03.png | pose_01 | a knight in silver armor in a medieval castle courtyard, oil painting style |
| output_02.png | pose_02 | (output_01과 같은 프롬프트) |
| output_03.png | pose_03 | (output_01과 같은 프롬프트) |
| output_03_sky.png | pose_03 | a young man in a green hoodie and jeans flying high in the bright blue sky above white clouds, one arm reaching up to the sky, wind in his hair, detailed realistic face, sharp eyes, full body, photorealistic (시드 7) |
| scale_0.5.png | pose_01 | (output_01과 같은 프롬프트, controlnet_conditioning_scale=0.5) |
| scale_1.0.png | pose_01 | (output_01과 같은 프롬프트, controlnet_conditioning_scale=1.0) |
| scale_1.5.png | pose_01 | (output_01과 같은 프롬프트, controlnet_conditioning_scale=1.5) |

## 참조 사진 2를 만든 프롬프트 (Realistic Vision txt2img, 시드 7, 30스텝)
full body photo of a young man standing and raising both arms straight up in the air, arms wide open, whole body visible from head to feet, detailed realistic face, plain white studio background

## 바꾼 프롬프트 기록 (포즈 3)
- 처음: `a superhero in a red cape flying high in the bright blue sky above white clouds, one fist raised to the sky, full body, photorealistic` → 유명 만화 캐릭터와 거의 같은 그림이 나와 사용하지 않음
- 바꾼 뒤, 시드 42 → 안전 필터가 잘못 걸려 검은 그림 → 시드 7로 다시 생성

## 수정 전 설정 (얼굴 품질 개선 전, samples/before_*.png)
- 모델: 기본 Stable Diffusion 1.5, 스텝 20, 네거티브 `lowres, blurry, deformed hands, extra limbs`
- 프롬프트에 얼굴 묘사 없음
