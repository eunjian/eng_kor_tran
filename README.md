# 영어-한글 변환 코드 설명 및 사용법
## 개요
이 코드는 영어 입력을 한국어로 변환하는 기능을 제공합니다. 주어진 영어 단어를 한국어 자모음으로 변환하고, 이를 조합하여 한글 음절을 생성합니다. 초성, 중성, 종성을 분리하고 결합하는 로직을 통해 정확한 한글 변환을 수행합니다.

## 사용법
1. **영어 입력**: 변환하려는 영어 단어 또는 문장을 입력합니다.
2. **변환 함수 호출**: eng2kor_transformer() 함수에 입력값을 전달하여 변환을 실행합니다.
3. **결과 출력**: 변환된 한글 결과를 확인합니다.

## 코드 설명
### 1. eng_to_kor():
  - 입력된 영어 문자열을 한국어 자모음으로 변환합니다.
  - ko_dict 딕셔너리를 사용하여 각 영어 알파벳에 해당하는 한국어 자모음을 찾습니다.
  - 변환된 자모음을 리스트 형태로 반환합니다.
### 2. syllable_seperator():
  - 변환된 자모음 리스트를 음절 단위로 분리합니다.
  - 초성, 중성, 종성의 조합 규칙에 따라 음절을 구분합니다.
  - 분리된 음절들을 리스트 형태로 반환합니다.
### 3. double_cons():
  - 겹받침이 만들어질 수 있는 연속된 자음을 겹받침으로 변환합니다.
  - double_consonant_map 딕셔너리를 사용하여 쌍자음 변환 규칙을 적용합니다.
### 4. double_vowel():
  - 연속된 모음들 중에서 이중 음으로 변환이 가능하면, 이중모음으로 변환합니다.
  - double_vowel_map 딕셔너리를 사용하여 이중모음 변환 규칙을 적용합니다.
### 5. separerate_cho_joong_jong():
  - 음절을 초성, 중성, 종성으로 분리합니다.
  - 자모음의 위치를 기반으로 분리 작업을 수행합니다.
### 6. combine_syllable():
  - 분리된 초성, 중성, 종성을 결합하여 한글 음절을 생성합니다.
  - 유니코드 조합 규칙을 사용하여 음절을 합칩니다.
### 7. eng2kor_transformer():
  - 전체 변환 과정을 수행하는 메인 함수입니다.
  - 입력 문자열을 공백으로 분리하여 각 단어를 변환합니다.
  - 변환된 단어들을 다시 결합하여 최종 결과를 반환합니다.

## 예제
```
input = "dlwpsms dnflrk gpdjwudi gkf tlrks"
result = eng2kor_transformer(input)
print(result)  # 이제는 우리가 헤어져야 할 시간
```

## 추가 정보
  - 이 코드는 Google Colab 환경에서 Python으로 작성되었습니다.
  - 코드 실행을 위해서는 Python 3.11 버전이 필요합니다.
  - 추가적인 한국어 자모음 변환 규칙을 ko_dict에 추가하여 변환 기능을 확장할 수 있습니다.
