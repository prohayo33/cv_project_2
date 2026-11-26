# 상품 이미지 카테고리 분류
이미지 입력으로 원피스/재킷/바지/스커트/상의를 예측합니다. 정답은 metadata.csv의 target_id입니다.
image_path는 이 폴더 기준 상대 경로입니다. 클래스별 하위 폴더는 없으므로 CSV 기반 Dataset을 사용하세요.
같은 상품의 여러 사진은 같은 분할에 들어갑니다. 사람/브랜드 단위 분할을 보장하지는 않습니다.
카테고리/하위분류/product_id/파일 경로는 모델 입력에 쓰지 마세요. 상품 설명과 검출 점수는 운영자용으로 분리했습니다.

같은 분할에서 ResNet18 Scratch와 ImageNet 사전학습 Transfer Learning을 비교합니다.
Macro F1/Accuracy/클래스별 Recall/혼동행렬/학습곡선/학습시간과 GPU를 기록하세요.
모델 선택과 개선 실험은 Val, Test는 최종 모델 결정 뒤 평가에 사용합니다.
증강은 Train에만 적용합니다. 비율 유지 Resize+Padding 등으로 224×224 입력을 만들 수 있습니다.
검출 결과로 잘린 영역이 부정확할 수 있으므로 의류 잘림/배경/착용사진의 오류 사례를 분석하세요.
공식 분할에서 상품 겹침과 중복을 정리하고 일부만 선택한 교육용 데이터입니다.
정답은 의류 카테고리이며 상품 검색/멀티모달 모델링은 이번 필수 범위가 아닙니다.
출처: Han et al., Automatic Spatially-aware Fashion Concept Discovery, ICCV 2017, Fashion200K.
원본 이미지의 이용/재배포 조건을 따르세요.
