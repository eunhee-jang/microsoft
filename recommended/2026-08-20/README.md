# Daily paper recommendations — 2026-08-20

## 검색 개요

- **연구 기준일**: 2026-08-20 (요청된 날짜 없음 → Asia/Seoul 기준 어제)
- **검색 창**: 1일(2026-08-20~2026-08-20) → 결과 없음 → 7일(2026-08-14~2026-08-20) → 결과 없음 → 30일(2026-07-22~2026-08-20) → 관련 논문 확보
- **검색 쿼리**: `chest X-ray deep learning classification` (교차 확인 쿼리: `chest radiograph multi-label pathology detection external validation`)

## 코호트 요약 (환자 단위 값 없음)

- 총 272건의 영상, 153명의 고유 환자
- 성별: 남 136 / 여 136 (균형)
- 연령 범위 9–87세, 평균 약 51.5세
- 촬영 자세: PA 184건, AP 88건
- 소견 라벨: No Finding 145건이 최다이며, 이외 Infiltration(21), Atelectasis(16), Nodule(7), Fibrosis(6), Effusion(6), Cardiomegaly(5), Pneumothorax(5) 등 단일 소견과 더불어 Effusion+Infiltration(5), Effusion+Pneumothorax(4), Atelectasis+Infiltration(4) 등 다중 라벨(동시 발생) 사례가 다수 존재
- 단일 기관 자료로, 기관 간 일반화 검증은 이 코호트만으로는 어려움

## 채택 논문

### 1. CLEAR: an auditable foundation model for radiology grounded in clinical concepts (Nature Biomedical Engineering)
개념 임베딩 기반 흉부 X-ray 파운데이션 모델로 4개 대륙, 4개 독립 코호트에서 외부 검증했다. 우리 코호트의 다중 라벨 흉부 소견(예: Effusion+Infiltration)에 대한 해석 가능한 예측 근거 제공 방식이 참고할 만하다. 다만 우리 데이터(153명, 단일 기관)로는 CLEAR가 보고한 대규모 외부 검증 성능을 재현·반증할 수 없다.
- https://doi.org/10.1038/s41551-026-01741-4

### 2. Grounding Radiology Report Findings into Medical Image Segmentation (npj Digital Medicine)
판독 보고서 텍스트만으로 흉부 X-ray 병변의 공간적 위치를 추정하는 CF2Seg를 53,386건 다기관 벤치마크에서 검증했다. 우리 코호트의 report_text에 다병변이 함께 기술된 사례가 많아, 픽셀 단위 주석이 없는 우리 데이터에도 적용 가능한 접근으로 유용하다. 우리 데이터에는 전문가 분할 주석이 없어 정확도 직접 검증은 불가능하다.
- https://doi.org/10.1038/s41746-026-03051-0

### 3. A foundation model for acute abdomen diagnosis stratification and triage on noncontrast computed tomography (Nature Communications)
비조영 복부 CT 응급 진단 AI를 다기관 외부 코호트(2528명)와 다중 판독자 교차 연구로 검증, AI 보조로 판독 정확도(AUROC 0.812→0.924)와 판독 시간이 개선됨을 보였다. 검증 설계(외부 코호트 + 다중 판독자 크로스오버)가 우리 흉부 X-ray 분류기 검증 계획에 참고할 모델이다. 영상 부위·모달리티가 달라 직접적 수치 비교는 불가능하다.
- https://doi.org/10.1038/s41467-026-76634-w

## 분석 축 (axes)

- **기관 간 일반화**: 단일 기관 자료를 넘어선 외부 검증 여부
- **다중 라벨 소견 해석가능성**: 동시 발생 소견에 대한 모델 설명력
- **판독의 임상적 실용성**: 판독자 보조 효과의 실측(정확도, 시간)

## 검토 안내

이 추천은 자동 검색 및 요약 결과이며, 임상 적용 전 반드시 담당 의료진의 검토가 필요합니다.
