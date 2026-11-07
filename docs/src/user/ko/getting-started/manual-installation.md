<!-- source: docs/src/user/en/getting-started/manual-installation.md @ 397ffc3 -->
# 직접 설치하기

이 페이지에서는 설치 프로그램 없이 WowVision을 설치하는 방법을 설명합니다. 설치 프로그램이 실행되지 않는 Mac에서, 또는 애드온을 직접 관리하고 싶을 때 이 방법을 씁니다. Windows에서는 [설치 프로그램](./installer.md)이 더 쉽고 이 모든 일을 대신 해 줍니다.

파일을 제자리에 두었으면 [애드온 켜기](./installation.md#애드온-켜기)로 넘어갑니다.

## 내려받기

WowVision은 GitHub에 올라옵니다. 내려받을 수 있는 것은 두 종류이고, 어느 쪽이든 zip 파일 하나입니다.

- 최신 릴리스. 안정 버전입니다. [WowVision 릴리스 페이지](https://github.com/wow-vision/WowVision/releases/latest)에서 내려받습니다. zip 이름은 버전을 따릅니다(예: WowVision-V1.0.0.zip). 용량이 큽니다(약 100MB).
- 베타 프리릴리스. 릴리스와 릴리스 사이에는 beta라는 프리릴리스가 하나 있습니다. 개발자가 무언가를 바꿀 때마다 다시 만들어지므로 테스터용입니다. 늘 같은 주소인 [베타 프리릴리스 페이지](https://github.com/wow-vision/WowVision/releases/tag/beta)에 있습니다. zip 파일 자체는 항상 https://github.com/wow-vision/WowVision/releases/download/beta/WowVision-beta.zip 에 있습니다. 그 페이지의 릴리스 노트에 지난 릴리스 이후의 모든 변경 사항이 있습니다.

두 종류 모두 같은 방법으로 설치합니다. 이미 설치된 예전 버전 위에 베타를 설치하면 기존 파일을 덮어쓸 뿐입니다.

### zip 안에 든 것

zip의 최상위에는 애드온 폴더가 두 개 있습니다.

- WowVision: 애드온 본체입니다. 모든 게임 버전에 필요한 것이 다 들어 있고, 번역과 WowVision이 재생하는 소리와 음성 녹음도 포함됩니다. 번역이나 오디오를 따로 내려받을 필요가 없습니다.
- WowVision_MapData_TBC: 클래식 경로의 지도 데이터입니다. 불타는 성전 기념 서버에서 길 안내(F10 창과 경로)가 동작하게 해 줍니다. [길 안내](../world/navigation.md)를 참고하십시오. WoW: Forever는 기본으로 WowNav로 경로를 찾고, 그 데이터는 이미 WowVision 폴더 안에 있습니다([WowNav](../world/wownav.md) 참고). WoW: Forever는 WowNav를 끈 경우에만 이 폴더를 씁니다. 다른 게임 버전에는 쓰이지 않으므로 그 버전들에서는 빼도 됩니다.

두 폴더는 한 번의 압축 풀기로 함께 설치됩니다. 다른 사람이 배포하는 다른 지도 데이터 애드온도 그 옆에 설치할 수 있습니다.

## 어디에 두는가

플레이하는 게임 버전의 AddOns 폴더에 zip을 풉니다. 게임 버전마다 World of Warcraft 설치 폴더 안에 전용 폴더가 있습니다. 보통 설치 폴더는 C:\Program Files (x86)\World of Warcraft\ 입니다. Mac에서는 보통 응용 프로그램 폴더 안의 World of Warcraft이고, 그 안에 같은 버전 폴더들이 있습니다.

| 게임 버전 | 설치 폴더 안의 폴더 | AddOns 폴더 |
|---|---|---|
| Classic Era(Vanilla) | `_classic_era_` | `_classic_era_\Interface\AddOns` |
| 불타는 성전(TBC) 기념 서버 | `_anniversary_` | `_anniversary_\Interface\AddOns` |
| 판다리아의 안개(Mists) | `_classic_` | `_classic_\Interface\AddOns` |
| Retail | `_retail_` | `_retail_\Interface\AddOns` |
| WoW: Forever | `_forever_` | `_forever_\Interface\AddOns` |

Interface 폴더와 AddOns 폴더가 아직 없으면 만듭니다. 여러 버전을 플레이한다면 버전마다 AddOns 폴더에 zip을 한 번씩 풉니다.

예: 불타는 성전을 플레이한다면 C:\Program Files (x86)\World of Warcraft\_anniversary_\Interface\AddOns에 zip을 풉니다. 그러면 그 AddOns 폴더 안에 WowVision 폴더와 WowVision_MapData_TBC 폴더가 생깁니다.

### 올바른 폴더 구조

압축을 푼 뒤 AddOns 폴더에는 다음이 있어야 합니다.

- `WowVision`
  - `WowVision_Vanilla.toc`
  - `WowVision_TBC.toc`
  - `WowVision_Mists.toc`
  - `WowVision_Standard.toc`
  - `WowVision_Camelot.toc`
  - `core`, `classic`, `retail`, `libs` 등의 폴더
- `WowVision_MapData_TBC`
  - `WowVision_MapData_TBC.toc`
  - 그리고 지도 파일들

확인 방법: TOC 파일이 WowVision 폴더 바로 안에 있어야 합니다.

### 흔한 실수: 겹친 폴더

압축 프로그램 중에는 "zip 이름으로 새 폴더를 만들어 풀기"를 권하는 것이 많습니다. 이를 받아들이면 폴더 안에 폴더가 생겨 TOC 파일이 AddOns\WowVision\WowVision\WowVision_Standard.toc에 놓일 수 있습니다. 그러면 게임이 애드온을 전혀 찾지 못하고, WowVision은 아무 알림 없이 불러와지지 않습니다. zip을 바탕 화면에 푼 뒤 zip 안의 폴더를 WowVision이라는 폴더 안에 복사해도 같은 일이 생깁니다.

고치려면 안쪽 WowVision 폴더를 위로 옮겨 TOC 파일이 한 단계 위에 오게 하고, 비어 있는 바깥 폴더를 지웁니다. 항상 AddOns 폴더에 바로 풀어서, 두 폴더가 zip에서 그대로 만들어지게 합니다.

## TOC 파일 다섯 개

TOC 파일은 애드온이 무엇이고 어떤 파일을 불러올지 게임에 알려 주는 작은 목록입니다. WowVision에는 게임 버전별 TOC 파일이 하나씩 들어 있고, 게임이 알맞은 파일을 스스로 고릅니다. 직접 고를 일은 없습니다.

| 게임 버전 | 쓰이는 TOC 파일 | 불러오는 것 |
|---|---|---|
| Classic Era | `WowVision_Vanilla.toc` | 공통 코어, 클래식 공통 모듈, Classic Era 모듈 |
| 불타는 성전 | `WowVision_TBC.toc` | 코어, 클래식 공통 모듈, 불타는 성전 모듈 |
| 판다리아의 안개 | `WowVision_Mists.toc` | 코어, 클래식 공통 모듈, 판다리아의 안개 모듈 |
| Retail | `WowVision_Standard.toc` | 코어와 Retail 모듈 |
| WoW: Forever | `WowVision_Camelot.toc` | 코어, Retail 모듈, Forever 모듈(Forever 클라이언트가 클래식·판다리아의 안개 클라이언트와 함께 쓰는 창 때문에 클래식·판다리아의 안개 부분도 몇 개 포함) |

버전을 고르는 설정은 없습니다. 기능이 일부 버전에만 있으면 설명서에 (Retail과 WoW: Forever 전용)처럼 적혀 있습니다. 전체 표는 [버전](../reference/versions.md)을 참고하십시오.

## 번역과 소리

WowVision에는 영어, 독일어, 프랑스어, 한국어 문구가 들어 있습니다. 어느 것을 쓸지는 게임 클라이언트 언어가 정하고, 그 밖의 클라이언트 언어에서는 영어로 표시됩니다.

소리, 비컨 소리, 녹음된 음성(음성 팩)도 WowVision 폴더 안에 있습니다. "소리 누락" 문제가 생기면 압축이 잘못 풀렸거나 일부만 풀린 것이 원인입니다. 폴더를 지우고 zip을 다시 풉니다.

## 직접 업데이트하기

1. 게임을 완전히 종료합니다.
2. 더 새 릴리스나 베타 zip을 내려받습니다.
3. 처음 설치할 때처럼 같은 AddOns 폴더에 풀고, 파일을 교체하는 데 동의합니다. 깔끔하게 업데이트하려면 먼저 예전 WowVision 폴더와 WowVision_MapData_TBC 폴더를 지워서 예전 버전 파일이 남지 않게 합니다. 설정은 이 폴더들에 있지 않으므로 사라지지 않습니다.
4. 게임을 시작하고 접속합니다. /wv version을 입력하면 새 버전을 볼 수 있습니다.

## 다음 단계

- [애드온 켜기](./installation.md#애드온-켜기)와 [처음 로그인하기](./first-login.md#월드에-들어간-뒤).
- [문제 해결](./troubleshooting.md): WowVision이 불러와지지 않을 때.
