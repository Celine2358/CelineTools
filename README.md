# CelineTools
# CelineTools v1.1 — 사용 설명서 (README)
<img width="433.5" height="353" alt="CelineToolsIcon" src="https://github.com/user-attachments/assets/28fce5fb-e0c8-4793-ad3c-a2e9d3756bff" />

**버전**: 1.1.0  
**작성일**: 2026-03-19
**앱 유형**: 게임 개발용 멀티 리소스 데스크톱 툴  
**플랫폼**: Windows 10/11 (x64)  
**제작자**: 셀리느  

---

## 1) 소개

**CelineTools**는 게임 개발 과정에서 자주 필요한 리소스 작업을 도와주는 **데스크톱 유틸리티 툴**입니다.  
기존 `CelineSheet v1.0`의 **GIF → 스프라이트 시트 변환 기능**을 확장하여, v1.1에서는 다음 기능을 하나의 프로그램 안에 통합했습니다.

- **GIF → Sprite Sheet PNG 변환**
- **오디오 Gain / Peak Normalize**
- **다중 오디오 파일 배치 처리**
- **MP4 → MP3 변환**

즉, 애니메이션 리소스와 오디오 리소스를 한 곳에서 정리할 수 있는 **개발 보조 툴**입니다.

---

## 2) 주요 기능

### Sprite Sheet 탭
- GIF 파일 정보 읽기
- 프레임 수 / 해상도 표시
- 행/열 자동 추천
- PNG 스프라이트 시트 생성
- 결과 프리뷰

### Audio 탭
- MP3 / WAV 파일 다중 선택
- **Gain (dB 직접 증감)**
- **Peak Normalize (목표 dBFS 기준 자동 보정)**
- 선택 파일 분석 표시
  - Peak
  - RMS
  - Duration
  - Sample Rate
  - Channels
- 배치 처리 진행률 표시
- 취소 버튼
- 실패해도 계속 진행 옵션
- 처리 후 폴더 자동 열기
- 같은 파일명 충돌 회피
- 로그 파일 저장
- 결과 요약 팝업
- MP3 Bitrate 선택
  - 128 / 192 / 256 / 320 kbps
- Gain 제한 해제(고급 모드)

### Converter 탭
- MP4 파일 선택
- FFmpeg를 사용한 MP4 → MP3 변환
- MP3 Bitrate 선택
- 결과 폴더 열기
- 완료 팝업 표시

---

## 3) 설치 및 실행

1. 배포된 ZIP 파일을 원하는 폴더에 압축 해제합니다.  
2. 폴더 안의 **`CelineTools.exe`**를 실행합니다.
3. SmartScreen 경고가 뜨면 **추가 정보 → 실행**을 선택합니다.

> `Tools/ffmpeg.exe` 파일은 Converter 기능에 필요합니다.  
> 삭제하거나 누락되면 MP4 → MP3 변환이 동작하지 않습니다.

---

## 4) 탭별 사용법

---

## 4-1) Sprite Sheet 탭

### 사용 순서
1. **찾아보기** 버튼으로 GIF 파일을 선택합니다.
2. **정보 읽기**를 눌러 GIF의 해상도와 프레임 수를 확인합니다.
3. **열/행 자동 추천**으로 추천값을 채우거나 직접 Rows / Columns 값을 입력합니다.
4. **스프라이트 시트 생성(Downloads)** 버튼을 눌러 PNG 파일을 생성합니다.
5. 생성이 완료되면 아래 프리뷰에서 결과를 확인할 수 있습니다.

### 출력 파일명 예시
`run_sheet_5x2.png`

### 저장 위치
- 기본 저장 위치: **Downloads**
- Downloads 폴더를 찾을 수 없으면 Desktop을 폴백으로 사용

---

## 4-2) Audio 탭

### 지원 형식
- 입력: **.mp3**, **.wav**
- 출력: **WAV**, **MP3**

### 사용 순서
1. **오디오 파일 선택(다중 선택)** 버튼으로 파일을 추가합니다.
2. 작업 선택:
   - **Gain (dB 조절)**
   - **Peak Normalize**
3. 필요 값 입력:
   - Gain 작업: `Gain dB`
   - Normalize 작업: `Target dBFS`
4. 출력 형식을 선택합니다.
5. MP3 출력일 경우 bitrate를 선택합니다.
6. **실행** 버튼을 눌러 배치 처리를 시작합니다.
7. 진행률, 로그, 결과 팝업을 확인합니다.

### 부가 기능
- **선택 항목 제거**
- **목록 비우기**
- **실패해도 계속 진행**
- **처리 후 폴더 자동 열기**
- **Gain 제한 해제** 체크박스

---

## 4-3) Converter 탭

### 사용 순서
1. **찾아보기** 버튼으로 MP4 파일을 선택합니다.
2. 원하는 MP3 Bitrate를 선택합니다.
3. **MP3로 변환** 버튼을 누릅니다.
4. 변환 완료 후 결과 파일과 폴더를 확인합니다.

### 출력 위치
`Downloads/CelineTools/Converter`

### 주의
이 기능은 내부적으로 **FFmpeg**를 사용합니다.  
`Tools/ffmpeg.exe`가 존재해야 정상 작동합니다.

---

## 5) Audio 기능 설명

---

## 5-1) Gain이란?

Gain은 사용자가 직접 입력한 dB만큼 전체 파형을 증감하는 방식입니다.

예:
- `+3 dB` → 조금 키움
- `+6 dB` → 진폭 약 2배
- `-6 dB` → 진폭 약 절반

즉, 현재 파일 상태를 고려하지 않고 **고정된 양만큼 볼륨을 올리거나 내리는 방식**입니다.

---

## 5-2) Peak Normalize란?

Peak Normalize는 파일의 **가장 큰 Peak**가 사용자가 지정한 `Target dBFS`에 맞도록 자동으로 Gain을 계산하는 방식입니다.

예:
- 현재 Peak = `-8.5 dBFS`
- 목표 Peak = `-1.0 dBFS`

필요 Gain:  
`-1.0 - (-8.5) = +7.5 dB`

즉, 파일마다 자동으로 다른 Gain이 적용되어 최종 Peak를 맞춥니다.

---

## 5-3) Peak / RMS란?

### Peak
파일 전체에서 가장 큰 절대 진폭입니다.  
순간적으로 가장 크게 튀는 지점을 의미합니다.

### RMS
평균적인 에너지 크기에 가까운 값입니다.  
체감 평균 볼륨 쪽에 더 가까운 참고 지표입니다.

---

## 5-4) dB와 dBFS

### dB
비율을 로그로 표현한 단위입니다.  
오디오에서 진폭 기준으로는 보통 다음 공식을 사용합니다:

- `dB = 20 * log10(amplitude)`
- `amplitude = 10^(dB / 20)`

### dBFS
디지털 오디오 최대치를 0으로 두는 척도입니다.

- `0 dBFS` = 디지털 최대치
- `-1 dBFS` = 최대보다 1 dB 낮음
- `-6 dBFS` = 여유 있음

**중요:**  
디지털 오디오에서는 **0 dBFS가 천장**입니다.  
이를 넘으려 하면 클리핑이 발생할 수 있습니다.

---

## 5-5) 클리핑 검사

Audio 탭에서는 Gain 작업 시 예상 Peak를 계산하여,  
안전 범위를 넘는 경우 실행 전에 경고를 표시합니다.

기본 권장 상한:
- MP3 출력: **-1.0 dBFS**
- WAV 출력: **-0.1 dBFS**

### Gain 제한 해제
`Gain 제한 해제` 체크 시:
- Gain dB 범위 제한 해제
- 클리핑 차단 해제
- 대신 경고 로그를 남긴 뒤 실행 가능

기본값은 **비활성화(false)** 입니다.

---

## 5-6) MP3 Bitrate 가이드

지원 옵션:
- 128 kbps
- 192 kbps
- 256 kbps
- 320 kbps

추천 기준:
- **128 kbps**: 용량 절약용
- **192 kbps**: 기본값으로 쓰기 좋은 고품질
- **256 kbps**: 품질과 용량의 균형
- **320 kbps**: MP3에서 가장 높은 쪽의 안전한 선택

기본 추천값은 **192 kbps**입니다.

---

## 6) 저장 위치

### Sprite Sheet
- `Downloads`

### Audio
- `Downloads/CelineTools/Audio`

### Converter
- `Downloads/CelineTools/Converter`

### 로그 파일
- `Downloads/CelineTools/Audio/logs`

---

## 7) 기술 스택

- **Avalonia UI 11.3.12**
- **Magick.NET-Q16-AnyCPU 14.10.4**
- **NAudio 2.2.1**
- **NAudio.Lame 2.1.0**
- **FFmpeg**
- **CommunityToolkit.Mvvm 8.4.0**

---

## 8) 트러블슈팅 / FAQ

### Q1. Audio 탭에서 Gain 적용이 막히고 클리핑 경고가 뜹니다.
A. 선택한 Gain 값으로 처리하면 예상 Peak가 안전 범위를 넘는 상황입니다.  
Gain 값을 낮추거나, `Peak Normalize`를 사용하거나, 필요 시 `Gain 제한 해제`를 사용하세요.

### Q2. MP4 → MP3 변환이 되지 않습니다.
A. `Tools/ffmpeg.exe`가 존재하는지 확인하세요.  
누락되면 Converter 기능이 동작하지 않습니다.

### Q3. 출력 파일명이 겹칩니다.
A. 프로그램이 자동으로 `(1)`, `(2)` 같은 번호를 붙여 충돌을 회피합니다.

### Q4. Downloads 폴더 대신 다른 곳에 저장되나요?
A. 기본은 Downloads지만, 시스템 환경에 따라 Desktop을 폴백으로 사용할 수 있습니다.

### Q5. 프로그램 내부 이름에 아직 CelineSheet가 보입니다.
A. v1.1은 기존 `CelineSheet` 프로젝트를 확장한 버전입니다.  
제품명과 툴명은 **CelineTools**로 정리되어 있으며, 내부 네임스페이스 일부는 차후 버전에서 정리 예정입니다.

---

## 9) 오프라인 동작 및 개인정보

- 본 프로그램은 네트워크 기반 서비스가 아닌 **로컬 실행형 데스크톱 툴**입니다.
- GIF / Audio / MP4 파일은 사용자의 로컬 디스크에서만 처리됩니다.
- Converter 기능 역시 네트워크를 사용하지 않고, 로컬의 FFmpeg를 실행합니다.

---

## 10) 변경 이력

### v1.0.0 — CelineSheet
- GIF 정보 읽기
- 행/열 자동 추천
- PNG 스프라이트 시트 생성
- 프리뷰 표시

### v1.1.0 — CelineTools
- Audio 탭 추가
- Gain / Peak Normalize
- MP3/WAV 다중 파일 배치 처리
- Peak / RMS / Duration / SampleRate / Channels 분석 표시
- 진행률 / 취소 버튼
- 실패 무시 옵션
- 처리 후 폴더 자동 열기
- 로그 파일 저장
- MP3 bitrate 옵션
- 결과 팝업
- Gain 제한 해제
- MP4 → MP3 Converter 추가
- FFmpeg 연동

---

## 11) 라이선스 및 고지

- **Avalonia** — MIT
- **Magick.NET / ImageMagick** — 해당 라이선스 준수
- **NAudio / NAudio.Lame** — 해당 라이선스 준수
- **Galmuri9** — 폰트 라이선스 확인 권장
- **FFmpeg** — 별도 배포 및 라이선스 고지 확인 권장

배포 시에는 각 라이브러리와 도구의 라이선스 고지를 함께 확인하는 것을 권장합니다.

---

## 12) 제작자

- **셀리느**
- 개인 게임 개발 및 리소스 제작 보조 툴 프로젝트

---

## 13) 한 줄 요약

**CelineTools v1.1**은  
GIF 스프라이트 시트 생성, 오디오 Gain/Peak Normalize 배치 처리, MP4→MP3 변환을 지원하는  
**게임 개발용 멀티 리소스 데스크톱 툴**입니다.
