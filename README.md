# 실험실 NH4 계산 프로그램

이 프로그램은 실험실에서 NH4 농도를 계산하기 위한 도구입니다. 여러 시료의 적정량을 입력하면, 자동으로 NH4 농도를 계산해줍니다.

## 기능

- 여러 시료의 적정량 입력을 통한 NH4 농도 계산
- 결과를 쉽게 확인할 수 있는 직관적인 인터페이스
- 입력한 데이터를 초기화할 수 있는 "다시하기" 기능

## 설치

1. **Python 설치**: 이 프로그램은 Python으로 작성되었습니다. 먼저 [Python](https://www.python.org/downloads/)을 설치하세요.
2. **필수 라이브러리 설치**: 다음 명령어로 필요한 라이브러리를 설치하세요.
   ```bash
   pip install tkinter
    ```

## PyInstaller로 실행 파일 만들기

### 기본 명령어

<details>
  <summary>PyInstaller 명령어 및 옵션</summary>

  PyInstaller는 Python 스크립트를 독립 실행형 실행 파일로 패키징합니다.

  ```bash
  pyinstaller [OPTIONS] scriptname.py
 ```
  - -F, --onefile : 하나의 독립 실행 파일로 패키징 합니다.
  - -D, --onedir : 기본 옵션, 여러 파일로 분리하여 저장합니다.
  - -W, --windowed/ --noconsole : 콘솔 창을 숨깁니다.
    
   ```bash
pyinstaller -F scriptname.py
 ```

  - -i, --icon <icon파일> : 실행 파일의 아이콘을 설정합니다.
    
 ```bash
pyinstaller --icon=파일명.ico scriptname.py
 ```

  - -add-date "SRC;DEST" (windows) / -add-date "SRC:DEST" (unix) : 외부 데이터 파일을 포함합니다.
    
    - SRC : 포함할 파일 또는 디렉토리의 경로 (터미널 위치가 파일위치랑 동일할 경우 파일명만 입력하면됨)
    - DEST : 실행 파일 내에서 해당 파일 또는 디렉토리의 위치를 지정 ("." 만 입력하면 root 디렉토리에 위치하게됨)
    
 ```bash
pyinstaller --add-data "data.txt;." scriptname.py
 ```

</details>
