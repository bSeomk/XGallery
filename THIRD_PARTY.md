# 제3자 구성요소·대응 소스

XGallery 1.1.0의 실행 ZIP에는 라이선스 전문·저작권 고지를 포함합니다. 대응 소스와 빌드 정보는 같은 [공개 릴리스](https://github.com/bSeomk/XGallery/releases/tag/v1.1.0)에서 무료로 별도 제공합니다.

- [SOURCE.zip](https://github.com/bSeomk/XGallery/releases/download/v1.1.0/SOURCE.zip): 배포본과 대응하는 앱 소스
- [THIRD-PARTY-SOURCES.zip](https://github.com/bSeomk/XGallery/releases/download/v1.1.0/THIRD-PARTY-SOURCES.zip): 제3자 원본 소스, 패치, 빌드 레시피 및 출처/해시 잠금 파일
- [BUILD-INFO.zip](https://github.com/bSeomk/XGallery/releases/download/v1.1.0/BUILD-INFO.zip): 배포 태그·커밋·실행 파일/소스 해시, 실제 바이너리 구성 검사 및 재빌드 설명

위 파일들은 프로그램 실행에 필요하지 않습니다. 실행 ZIP을 다른 곳에서 재배포하는 경우에도 대응 소스의 제공과 각 라이선스 의무를 유지해야 합니다.

## 적용 라이선스

- 앱 자체 GUI·갤러리·수집 관리·업데이터: GPL-3.0-or-later. 전문은 `LICENSES/GPL-3.0.txt`에 있습니다.
- 별도 gallery-dl 1.32.19 수집기 및 어댑터: GPL-2.0-only. 전문은 `LICENSES/GPL-2.0.txt`와 `LICENSES/gallery_dl`에 있습니다.
- Qt/PySide6/Shiboken 6.10.1: 사용한 오픈 소스 구성에는 LGPL-3.0 및 해당 파일별 라이선스를 적용합니다. QtBase·QtMultimedia·QtSvg·QtImageFormats와 PySide 대응 소스를 제공합니다. LGPL/GPL 전문은 `LICENSES/UPSTREAM` 등 각 고지 폴더에 있습니다.
- Qt Multimedia의 FFmpeg 7.1.2: LGPL-2.1-or-later 및 파일별 라이선스. 실제 configure/license 기록은 BUILD-INFO.zip에 있습니다. GPL/nonfree 또는 libx264/libx265를 활성화한 이전 PyAV 구성은 배포하지 않습니다.
- Pillow 및 내장 코덱, Python 3.12.4, Requests와 관련 패키지, OpenSSL·SQLite·libffi·zlib·bzip2·expat·xz 등: `LICENSES`의 전문·고지와 제3자 소스 묶음을 확인하세요.
- 별도 7zr.exe 26.04: LGPL 및 7-Zip 고지 등 해당 조건. `LICENSES/7-Zip-LICENSE.txt`와 7-Zip 대응 소스를 제공합니다.
- PyInstaller: GPL 및 부트로더 예외 고지를 유지합니다.

Firefox는 실행 ZIP에 포함하지 않습니다. 앱이 처음 로그인 준비 시 Mozilla 공식 파일을 내려받아 서명을 확인합니다. 해당 소프트웨어에는 Mozilla의 라이선스가 적용됩니다. Microsoft Visual C++ Runtime·Windows ICU·UCRT/API-set DLL은 동봉하지 않으며 시스템 구성요소를 사용합니다. Runtime이 필요하면 README의 Microsoft 공식 설치 경로를 이용하세요.

사용하지 않는 geckodriver·Selenium·PyAV, Qt PDF/WebEngine/QML/Quick/가상 키보드 모듈은 포함하지 않습니다.

## 수정·교체·재링크

라이선스가 허용하는 소스 수정·역공학·라이브러리 교체·재링크 및 수정본 실행을 제한하는 별도 EULA를 두지 않습니다. 앱의 업데이트 서명은 원격 배포 파일의 인증에 사용하며 사용자의 로컬 라이브러리 교체를 막지 않습니다.

1. 앱을 종료하고 프로그램 폴더와 라이브러리를 백업합니다.
2. SOURCE.zip과 THIRD-PARTY-SOURCES.zip을 받습니다. 두 소스 묶음 및 BUILD-INFO.zip의 `BUILDING.md`에 재빌드·패치·레시피 위치를 안내합니다.
3. 호환되는 Qt/PySide/Shiboken 및 FFmpeg 공유 DLL을 빌드해 `_internal/PySide6`의 해당 묶음을 교체하거나, 제공된 앱 소스로 전체를 재빌드합니다. 서로 다른 FFmpeg 주 버전 DLL의 이름만 바꾸어 대체하지 마세요.
4. 로컬 수정본을 유지하려면 프로그램 업데이트에서 자동 다운로드를 끕니다. 기본 시작 검사와 제공 테스트로 수정본 동작을 확인합니다.

공식 Qt 휠과 Python 네이티브 DLL의 출처/해시, 실제 FFmpeg 구성 및 제외 파일은 빌드 도구로 검사합니다. 업스트림 바이너리의 비트 단위 재현이나 법률 적합성 인증을 주장하지 않습니다. 이 문서가 X의 이용 허가를 대신하지 않습니다.

공식 안내: [Qt 라이선스 의무](https://www.qt.io/development/open-source-lgpl-obligations), [FFmpeg](https://ffmpeg.org/legal.html), [7-Zip](https://www.7-zip.org/license.txt).
