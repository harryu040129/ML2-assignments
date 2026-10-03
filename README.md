# Machine Learning 2 — Assignments
한양대학교 데이터사이언스학과 Machine Learning 2 수업에서 작성한 알고리즘 구현과 이미지 분류 실험입니다.

## 과제 안내
| 노트북 | 데이터 / 주제 | 구현 내용 |
| --- | --- | --- |
| [KNN.ipynb](KNN.ipynb) | MNIST | 반복문과 브로드캐스팅 기반 k-NN, 거리 계산, 정확도 비교 |
| [SVM.ipynb](SVM.ipynb) | CIFAR-10 | 선형 SVM, hinge loss, one-vs-rest 분류, 다항 로지스틱 회귀 |
| [Image_Classification_3Models.ipynb](Image_Classification_3Models.ipynb) | 이미지 분류 | VGG19, MobileNet2, MobileResNet 및 클래스 불균형 실험 |

이미지 분류 노트북 두 개는 별도 파일로 보존되어 있습니다. 최종 성능 순위나 완전히 동일한 사본이라는 의미는 아닙니다.

## 실행 준비
```sh
python -m venv .venv
# macOS/Linux: source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
jupyter lab
```

- MNIST와 CIFAR-10은 torchvision으로 `./data`에 내려받으므로 첫 실행에 네트워크가 필요합니다.
- 이미지 분류는 노트북의 KaggleHub 다운로드 코드와 `train.csv`, `test.csv`, 이미지 경로를 먼저 확인합니다. 데이터 접근 권한과 실행 환경에 따라 경로 수정이 필요합니다.
- CNN 학습에는 GPU 사용을 권장합니다. 학습 시간과 메모리 사용량은 모델·배치 크기에 따라 달라집니다.
- `requirements.txt`는 import 기반 참고 목록입니다. PyTorch와 torchvision은 실행 장치에 맞는 호환 조합을 사용해야 하며, 전체 환경을 검증한 lockfile은 아닙니다.

## 학습 포인트
- 직접 구현한 손실함수와 PyTorch 모듈의 연결
- 데이터 정규화와 하이퍼파라미터 탐색
- 가중 손실, focal loss, sampling을 활용한 클래스 불균형 대응
- 모델별 실험 코드와 결과 해석

## 재현 상태
노트북은 수업 당시의 실험 기록이며, 여러 모델·함수 정의와 출력이 포함됩니다. 이번 문서 정리에서 전체 학습을 재실행하지 않았고, 저장된 출력은 새로 검증한 성능 수치가 아닙니다.
