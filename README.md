# 실험실 NH4, SS 계산 프로그램

이 프로그램은 실험실에서 NH4, SS, VSS 농도를 계산하기 위한 도구입니다. 여러 시료의 적정량을 입력하면, 자동으로 NH4, SS, VSS 농도를 계산해줍니다.

![NH4실행화면](https://github.com/user-attachments/assets/b349ed3c-5c61-4482-b04a-4fbdc77a6ece)
![ss계산기실행](https://github.com/user-attachments/assets/9691b76a-abf1-4254-a04d-0c19e9bd6d49)


## 기능

- 여러 시료의 적정량 입력을 통한 NH4 및 SS, VSS 농도 계산
- 결과를 쉽게 확인할 수 있는 직관적인 인터페이스
- 입력한 데이터를 초기화할 수 있는 "다시하기" 기능

## 설치

1. **Python 설치**: 이 프로그램은 Python으로 작성되었습니다. 먼저 [Python](https://www.python.org/downloads/)을 설치하세요.
2. **필수 라이브러리 설치**: 다음 명령어로 필요한 라이브러리를 설치하세요.
   ```bash
   pip install tkinter
   pip install pyinstaller
    ```

## PyInstaller로 실행 파일 만들기

### 기본 명령어

<details>
  <summary>PyInstaller 명령어 및 옵션</summary>

  PyInstaller는 Python 스크립트를 배포에 용이한 독립 실행형 실행 파일로 패키징합니다.

  ```bash
  pyinstaller [OPTIONS] scriptname.py
 ```
  - -F, --onefile : 하나의 독립 실행 파일로 패키징 합니다.
  - -D, --onedir : 기본 옵션, 여러 파일로 분리하여 저장합니다.
  - -w, --windowed/ --noconsole : 콘솔 창을 숨깁니다.
    
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

- --clean: 빌드 폴더와 캐시를 지우고 빌드합니다.
- --upx-dir <UPX_DIR>: UPX 압축기를 사용해 실행 파일을 더 작게 만듭니다.
- --specpath <DIR>: .spec 파일의 경로를 지정합니다.

 ```bash
pyinstaller --specpath=build scriptname.py
 ```

- --distpath <DIR>: 최종 실행 파일이 생성될 경로를 지정합니다.

 ```bash
pyinstaller --distpath=output scriptname.py
 ```

</details>

1. 프로그램 다운로드: 이 레포지토리를 클론하거나 ZIP 파일로 다운로드하세요.
 ```bash
git clone https://github.com/whidong/LabCalcTool.git
 ```
2. 터미널 또는 명령 프롬프트에서 프로그램이 있는 디렉토리로 이동하세요.
 ```bash
cd .../LabCalcTool
 ```
3. 이미지파일 및 icon 파일을 포함해서 실행파일로 만듭니다.

- NH4 실행파일
 ```bash
pyinstaller --icon=NH4.ico -F -w --add-data "NH4_formula.png;." NH4계산프로그램_v0.2.py
 ```

- SS 실행파일
 ```bash
pyinstaller --icon=ss.ico -F -w ss계산프로그램_v0.5.py
 ```
  

## 사용 방법

1. 프로그램을 실행하면 여러 시료의 적정량을 입력할 수 있는 창이 나타납니다.
2. 각 시료의 적정량을 입력한 후 "계산하기" 버튼을 눌러 결과를 확인하세요.
3. 잘못된 데이터를 입력했거나 다시 시작하려면 "다시하기" 버튼을 클릭하세요.

## 파일 구조
- NH4
   - NH4계산프로그램_v0.2.py : 메인 프로그램 파일
   - NH4_formula.png : 프로그램에서 NH4 계산식을 보여주기 위한 이미지 파일
   - NH4.ico : 프로그램 실행 아이콘 이미지

- SS
  - ss계산프로그램_v0.5.py : 메인 프로그램 파일
  - ss.ico : 프로그램 실행 아이콘 이미지








