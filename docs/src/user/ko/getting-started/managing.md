<!-- source: docs/src/user/en/getting-started/managing.md @ 397ffc3 -->
# WowVision 관리

WowVision이 설정을 어디에 보관하는지와 백업하는 법, WowVision을 업데이트하는 법, 제거하는 법을 설명합니다.

## 설정이 저장되는 곳

WowVision은 게임 자체의 저장 변수 파일에 데이터를 보관합니다. 게임은 플레이 중에는 이 파일을 기록하지 않고, 로그아웃하거나 /reload를 입력할 때 기록합니다. 게임이 비정상 종료되거나 작업 관리자로 게임을 닫으면 마지막 로그아웃이나 /reload 이후의 변경 사항은 사라집니다.

| 저장 변수 | 담는 내용 | 범위 |
|---|---|---|
| WowVisionGlobalDB | 기본적으로 대부분의 설정, 경보, 단축키, 버퍼와 모니터 | 계정 전체 |
| WowVisionDB | "이 캐릭터"로 옮긴 설정과 주문 기록 | 캐릭터마다 파일 하나 |
| WowVisionDump | 진단 기록: Lua 오류, 차단된 호출 기록, 컨트롤러 기록, 미니맵 걷기 로그, 퀘스트 점검 보고서 등 | 계정 전체 |
| WowVisionPriceDB | 경매 가격 데이터베이스(TBC 전용) | 계정 전체 |

파일은 WowVision을 설치한 게임 버전 폴더 안의 WTF 폴더에 있습니다.

- 계정 전체 파일: `WTF\Account\<ACCOUNT NAME>\SavedVariables\`에 있으며 이름은 WowVisionGlobalDB.lua와 WowVisionDump.lua이고, TBC에서는 WowVisionPriceDB.lua도 있습니다.
- 캐릭터별 파일: `WTF\Account\<ACCOUNT NAME>\<Realm>\<Character>\SavedVariables\WowVisionDB.lua`.

기본적으로 대부분의 설정은 모든 캐릭터가 함께 씁니다. 한 모듈의 설정을 한 캐릭터에서만 쓰도록 바꿀 수도 있습니다. WowVision 메뉴에서 해당 모듈에 초점을 두고 Shift+F10을 누른 뒤 범위를 고릅니다. 단축키(컨트롤러 버튼 포함)도 같은 방식으로 공유되며, 단축키 버튼에 따로 범위 항목이 있습니다. [WowVision 메뉴와 설정](../basics/menu-and-settings.md)과 [단축키](../basics/keybindings.md)를 참고하십시오.

설정을 백업하려면 게임을 닫은 상태에서 이 파일들을 복사합니다. 모든 것을 초기화하려면 게임을 닫은 상태에서 이 파일들을 지웁니다. 다음 로그인 때 WowVision이 기본값으로 시작합니다. 설정이 자꾸 사라지면 [설정이 사라짐](./troubleshooting.md#설정이-사라짐)을 참고하십시오.

## WowVision 업데이트

- 설치 프로그램으로: 바탕 화면이나 시작 메뉴의 바로 가기로 WowVision Updater를 실행하고 지금 업데이트를 고릅니다. [나중에 업데이트하기](./installer.md#나중에-업데이트하기)를 참고하십시오.
- 직접: 새 zip을 내려받아 기존 폴더를 새 폴더로 바꿉니다. [직접 업데이트하기](./manual-installation.md#직접-업데이트하기)를 참고하십시오.

업데이트에 필요하면 WowVision이 저장된 설정을 스스로 변환합니다. 릴리스 페이지의 릴리스 노트를 읽어 보십시오. 지난 릴리스 이후의 변경 사항과 초기화되는 항목이 나와 있습니다. 베타는 매번 같은 주소에서 교체되므로 원하는 만큼 자주 업데이트해도 됩니다.

## 제거

1. 게임을 닫습니다.
2. AddOns 폴더에서 WowVision 폴더와 WowVision_MapData_TBC 폴더를 지웁니다.
3. 저장된 설정까지 없애려면 위에 나온 WowVision 저장 변수 파일도 지웁니다.

WowVision이 첫 로그인 때 한 번 바꾼 행동 단축바 잠그기, 시점 전환 방식, 대화 메시지 사이 소리는 애드온을 제거한 뒤에도 게임에 그대로 남습니다. WowVision 설정으로 마우스 이동을 켜거나 껐다면 마우스 이동도 그대로 남습니다. 이전처럼 되돌리려면 [캐릭터의 첫 로그인 때 WowVision이 바꾸는 것](./first-login.md#캐릭터의-첫-로그인-때-wowvision이-바꾸는-것)에 설명된 대로 게임 설정에서 이 항목들을 바꿉니다.

설치 프로그램으로 설치했다면 추가 애드온, WoW Login Tool, 음성 옵션 같은 다른 것도 함께 설치됐을 수 있습니다. 이 항목들은 [설치 프로그램이 컴퓨터에 남기는 것](./installer.md#설치-프로그램이-컴퓨터에-남기는-것)에 나와 있습니다. 이 중 더 이상 필요 없는 항목의 폴더를 지우고, WowVision Updater 바로 가기도 지웁니다.
