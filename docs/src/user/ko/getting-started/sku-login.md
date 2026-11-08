<!-- source: docs/src/user/en/getting-started/sku-login.md @ 397ffc3 -->
# Sku Login Tool로 로그인하기

WowVision은 캐릭터가 월드에 들어선 뒤부터 동작합니다. 게임은 그 시점에야 애드온을 불러오므로, WowVision을 포함한 어떤 애드온도 그 전의 화면을 읽을 수 없습니다. 그 화면들에 접근할 수 있게 만들 수 있는 것은 게임 자체뿐입니다. WoW: Forever는 로그인 화면을 소리 내어 읽어 주지만 여전히 마우스가 필요하므로, 이 도구가 그곳에서도 도움이 됩니다. 로그인 화면, 서버 목록, 캐릭터 화면, 캐릭터 만들기를 통과하려면 Sku와 함께 제공되는 WoW Login Tool(버전 4.x)을 쓸 수 있습니다. 월드에 들어서자마자 WowVision이 이어받을 수 있도록, 이 페이지에서는 이 도구가 무엇인지, 어떻게 받는지, 어떻게 쓰는지 설명합니다.

## 도구 소개

WoW Login Tool은 게임과 함께 실행되는 작은 Windows 프로그램입니다. Sku 프로젝트의 "시작 메뉴" 도구입니다. 애드온이 아니며 WowVision의 일부도 아닙니다. 게임의 메모리를 읽거나 변경하지 않습니다. 비장애인 플레이어가 하듯이, 게임 창을 보고 키를 누르고 마우스를 클릭할 뿐입니다.

이 도구로 할 수 있는 일:

- 게임이 저절로 로그인하지 않았을 때 계정 화면에서 로그인합니다.
- 서버를 변경합니다.
- 캐릭터를 골라 월드에 들어갑니다.
- 이름 확인을 포함해 캐릭터를 만듭니다.
- 캐릭터를 삭제합니다.
- 게임의 팝업 메시지를 소리 내어 들려줍니다. 예: "name not available".

이 페이지는 WoW Login Tool 버전 4를 설명합니다. 도구는 시작할 때 자신의 버전 번호를 말합니다.

동작 방식은 게임 버전에 따라 다릅니다.

- Classic Era와 불타는 성전(TBC) 기념 서버에서는 도구가 Windows 문자 인식(OCR)으로 화면을 보고 자체 음성으로 읽어 줍니다. 실제 캐릭터 이름, 레벨, 직업, 지역과 실제 서버 목록을 알려 줍니다.
- WoW: Forever에서는 게임이 자체 TTS 음성으로 로그인 화면을 소리 내어 읽습니다. 그곳에서는 도구가 화면을 읽어 주지 않습니다. 대신 마우스를 항목에서 항목으로 옮겨 주고, 게임이 각 항목을 말합니다.

### 지원하는 게임 버전

| 게임 버전 | 버전 4.x 지원 여부 |
|---|---|
| Classic Era | 지원합니다. |
| 불타는 성전 기념 서버(2.5.x) | 지원합니다. |
| WoW: Forever(라이브 클라이언트) | 지원합니다. 모든 외형 옵션을 포함한 캐릭터 만들기 전체를 지원합니다. |
| 판다리아의 안개 클래식 | 지원하지 않습니다. 도구가 이 게임 버전은 아직 지원하지 않는다고 알립니다. |
| Retail과 대격변 클래식 | 설정에서 고를 수는 있지만 지원하지 않습니다. |

도구는 게임 버전을 스스로 알아냅니다("처음 시작하기" 참고). 리치 왕의 분노 클라이언트도 지원하지 않습니다.

## 필요한 것

- Windows 10 또는 Windows 11. 도구는 Windows에 내장된 기능(창 캡처와 문자 인식)을 쓰므로 인터넷으로 아무것도 보내지 않습니다.
- AutoHotkey 버전 2("받아서 설치하기" 참고).
- 게임 자체. 한 번 이상 실행한 적이 있어야 합니다.
- 스크린리더 음성 옵션을 쓰려면 NVDA. 아래 "음성과 낭독"을 보십시오.

Windows 문자 인식에는 게임 클라이언트의 언어가 필요합니다. 도구는 설정에서 고른 언어를 씁니다: 영어, 독일어, 프랑스어, 러시아어, 스페인어. Windows에 그 언어의 문자 인식이 없으면 도구는 Windows 프로필의 언어를 대신 사용합니다. 계속 동작하기는 하지만 이름과 서버를 잘못 읽을 수 있습니다.

Mac용 도구도 있지만 이 설명서에서는 다루지 않습니다.

## 받아서 설치하기

가장 쉬운 방법은 [WowVision 설치 프로그램](./installer.md)입니다. WoW Login Tool 설치 항목이 기본으로 체크되어 있습니다. WoW: Forever, 불타는 성전 기념 서버, Classic Era용으로 도구를 설치하고, 필요한 AutoHotkey를 함께 설치하고, 화면 인식 파일과 더 또렷한 글꼴을 Classic Era와 불타는 성전에 복사하고, 바탕 화면과 시작 메뉴에 WoW Login Tool 바로 가기를 만듭니다. 도구는 그 바로 가기로 시작하십시오.

### 직접 설치하기

1. [https://www.autohotkey.com/](https://www.autohotkey.com/)에서 AutoHotkey 버전 2를 설치합니다.
2. [WoW Login Tool 버전 4 다운로드 페이지](https://github.com/Sku75/Sku-WoW-Addon-TBC/releases/tag/login-tool)에서 WoW-Login-Tool.zip을 내려받습니다. 이 릴리스에는 항상 최신 도구가 있습니다. 압축을 풉니다. 안에 있는 폴더 이름은 WoW Login Tool입니다. 이 폴더는 World of Warcraft 폴더 안, 게임 버전 폴더들 옆에 두는 것이 가장 좋습니다. WoW: Forever에서는 도구가 그 위치나 기본 설치 폴더에서 게임의 설정 파일을 찾습니다.
3. 도구 폴더 안의 CopyTheContentOfThisFolderToInterface 폴더를 엽니다. 폴더 다섯 개가 들어 있습니다. 다섯 개를 모두 복사합니다.
4. World of Warcraft 설치 폴더(흔히 C:\Program Files (x86)\World of Warcraft)를 열고, 게임 버전의 폴더를 엽니다.
   - 불타는 성전 기념 서버는 _anniversary_
   - Classic Era는 _classic_era_
5. 그 안의 Interface 폴더를 열고 다섯 폴더를 붙여 넣습니다. 기존 파일을 덮어쓰는 데 동의합니다.
6. Classic Era와 TBC에서 권장: 도구의 fonts 폴더에 있는 install_wow_fonts.ps1 스크립트를 관리자 권한으로 실행합니다. 게임 글꼴을 문자 인식이 훨씬 잘 읽는 더 또렷한 글꼴로 교체합니다. 기본으로는 TBC 기념 서버 폴더에 적용됩니다. Classic Era에는 -ClientDir 매개변수로 폴더를 지정합니다. -Remove 매개변수는 변경을 되돌립니다. 변경은 다음에 게임을 시작할 때 적용됩니다.
7. v2 폴더의 START.ahk를 AutoHotkey 버전 2로 실행해 도구를 시작합니다.

WoW: Forever에서는 다섯 텍스처 폴더와 글꼴이 필요하지 않습니다.

설치할 때 알아 둘 것:

- 복사한 다섯 폴더는 이름이 같은 게임 인터페이스 파일을 덮어씁니다. 다른 애드온이 같은 파일을 변경하면 그 애드온도 영향을 받습니다. 도구가 "screen recognition textures are missing from the game folder"라고 말하면 다섯 텍스처 폴더를 다시 복사하십시오.
- 도구의 새 버전이 나오면 다섯 폴더를 다시 복사하십시오. 오래된 복사본 때문에 도구가 화면을 인식하지 못할 수 있습니다.

## 처음 시작하기

1. 도구를 시작합니다. "Login tool version"과 번호(예: 4.1)를 말합니다. 맨 처음 실행할 때는 "Setup mode"라고 말하고, 화살표 키로 네 가지를 이 순서대로 설정하라고 합니다: 음성("Go right to select a voice"), 언어, 지역(Europe 또는 USA), 게임 종류. 오른쪽 화살표로 들어가고, 위아래 화살표로 고르고, Enter를 눌러 확정합니다. 고를 때마다 "selected"로 확인해 줍니다. 마지막에 "Setup completed. Start the game now."가 들립니다.
2. 그 뒤 도구는 Pause mode가 되어 조용히 기다립니다.
3. 게임을 시작합니다. 도구가 게임 창을 보고 화면을 알아보면 "Login mode for" 뒤에 게임 버전, 지역, 언어를 말합니다. 예: "Login mode for Burning Crusade, Europe, English". 도구가 작업하는 동안에는 짧은 소리가 반복해서 들립니다. 그다음 "Main menu"라고 말합니다. 게임이 이미 실행 중이었다면 Alt+Tab을 눌러 게임 창으로 돌아가십시오.

도구는 게임 버전을 스스로 알아냅니다. 알아낸 버전이 설정에 저장된 버전과 다르면 전환하고 "game version detected"와 이름을 말합니다. 도구에 설정이 없는 클라이언트(예: 판다리아의 안개나 리치 왕의 분노)에서는 "This game version is not supported yet."과 버전 번호가 들립니다. 잘못 알아내면 메뉴의 Select game type으로 직접 지정하십시오. 선택지는 Cataclysm, Classic Era, Burning Crusade, Retail, WoW Forever입니다. 직접 고른 게임 종류는 고정됩니다. 같은 목록의 항목인 Detect game type automatically를 고르면 다시 자동으로 돌아갑니다.

나중에 언어, 지역, 게임 종류를 변경하면 도구가 스스로 다시 시작하므로("selected. Restarting script to apply. Please wait.") 버전을 다시 듣게 됩니다. 음성을 변경할 때는 다시 시작하지 않습니다.

Forever 클라이언트 팁:

- WoW: Forever보다 도구를 먼저 시작하십시오. 도구를 시작할 때 Forever 게임이 실행 중이 아니면 도구가 게임 설정에서 화면 낭독을 켜고, 게임을 처음 시작할 때 나오는 내레이터 질문을 끄고, 낭독 음성과 말하기 속도를 설정합니다. 무언가를 변경하면 "narration settings written for Forever"가 들립니다. 게임은 시작할 때만 이 설정을 읽습니다. 게임이 이미 실행 중이면 도구는 설정을 건드리지 않고 그에 대해 아무 말도 하지 않습니다.
- 처음 설치한 뒤 내 음성 대신 게임의 기본 음성이 들리면, 게임을 닫고 도구를 먼저 시작한 다음 게임을 시작하십시오.

## 모드

- Setup mode: 맨 처음 시작해 음성, 언어, 지역, 게임 종류를 고르는 동안에만 쓰입니다.
- Pause mode: 도구가 기다립니다. 게임 창에 초점이 없을 때는 언제나 이 모드입니다.
- Login mode: 로그인, 서버, 캐릭터 화면용 음성 메뉴입니다. 도구가 이 화면 중 하나를 보면 자동으로 시작합니다.
- Play mode: 월드에 들어선 상태입니다. 도구는 모든 키를 게임으로 넘깁니다. 여기서부터 WowVision(그리고 설치했다면 Sku)이 동작합니다.

도구는 모드를 스스로 변경합니다. 게임 창을 떠났다가 돌아올 때마다 주 메뉴에서 다시 시작합니다. 의도된 동작입니다. Alt+F1 키로 모드를 직접 전환합니다(키 표 참고).

도구가 Login mode와 Play mode 사이를 스스로 전환하지 않으면 Alt+F1을 누르십시오.

도구가 제대로 동작하게 하려면 다음을 지키십시오.

- 도구가 작업하며 대기 소리를 내는 동안에는 키를 누르거나, 클릭하거나, 마우스를 움직이거나, 창을 전환하지 마십시오.
- 게임 창을 앞에 두고 보이게 하십시오. 최소화한 채로 플레이하지 마십시오.
- 진행 중인 동작을 멈추려면 Alt+F1을 누르십시오.

## Classic Era와 TBC에서 도구 쓰기

### 계정 화면에서 로그인하기

게임이 저절로 로그인하지 못하면 계정 화면에 머뭅니다. 그러면 도구가 "Not logged in. Either there is no connection to the server, or account name and password still have to be entered in the game."이라고 말합니다. 이때 메뉴에는 로그인하지 않아도 쓸 수 있는 항목만 있습니다: Account name, Password, Log in, Save account name, 그다음 음성, 언어, 게임 종류, 지역, 버전.

1. Account name으로 이동해 Enter를 누릅니다. (오른쪽 화살표는 항목을 다시 말할 뿐입니다.) 입력란의 현재 내용(비어 있으면 "Account name: empty")이 들리고, 이어서 "Type now. Enter ends the entry, Escape leaves it."이 들립니다. 계정 이름을 입력하고 Enter를 누릅니다. 도구가 계정 이름을 다시 읽어 줍니다.
2. Password로 이동해 같은 방법으로 합니다. "Type now. The password is never read back."이 들립니다. 비밀번호는 절대 다시 읽어 주지 않으며, Enter는 로그인하지 않고 입력만 끝냅니다.
3. Log in을 골라 Enter를 누릅니다. "Logging in. Please wait."가 들립니다. 도구는 팝업(예: 비밀번호 오류)이 열리면 읽어 주고, 닫은 뒤 "The login did not go through."라고 말합니다. 게임이 연결 중일 뿐이면 도구는 메시지만 읽고 기다립니다.
4. Save account name은 게임 자체의 "remember account name" 확인란을 켜거나 끄고, "Save account name: on" 또는 "off"라고 말합니다.

입력란에 입력하는 동안 화살표 키는 게임으로 가므로 오타를 고칠 수 있습니다. 도구는 비밀번호를 저장하지 않으며 자동 로그인 기능도 없습니다. Battle.net 앱을 닫았다가 다시 여는 편이 다시 들어가는 데 더 빠른 경우가 많습니다. Forever에서는 대신 게임이 자체 로그인 화면을 낭독합니다.

### 주 메뉴

주 메뉴에는 다음 항목이 이 순서대로 있습니다.

1. Select character
2. Login with selected character
3. Create new character
4. Change server
5. Delete character
6. Select voice
7. Select language
8. Select game type
9. Select region
10. 버전 항목. "WoW Logintool V3.0, Version: V3.0"이라고 읽습니다. 이것은 도구의 릴리스 번호가 아닙니다. 릴리스 번호는 도구가 시작할 때 말합니다.

위아래 화살표로 항목 사이를 이동하고, 오른쪽 화살표로 하위 메뉴가 있는 항목에 들어가고, 왼쪽 화살표로 돌아가고, Enter로 항목을 실행합니다. 다른 언어에서는 문구가 다르며, 이후 버전에서 변경될 수 있습니다.

### 캐릭터를 골라 월드에 들어가기

1. Select character로 가서 오른쪽 화살표를 누릅니다. 도구가 캐릭터를 실제 이름, 레벨, 직업, 지역으로 나열합니다. 예: "1: Anna, level 1 Priest". 캐릭터가 없으면 "Empty. No characters on this server."가 들립니다.
2. 위아래 화살표로 캐릭터를 고르고(Page Down과 Page Up은 열 개씩 건너뜁니다) Enter를 누릅니다. 도구가 이름 뒤에 "selected"를 말하고 Login with selected character로 이동합니다.
3. Enter를 눌러 월드에 들어갑니다. 도구가 "Play mode"라고 말합니다. 말하지 않으면 Alt+F1을 누르십시오.
4. 새 캐릭터는 소개 영상으로 시작할 수 있습니다. 영상이 끝나면 월드에 서 있게 되고 WowVision이 넘겨받습니다.

캐릭터가 많은 서버에서는 세는 데 몇 초가 걸릴 수 있습니다. 도구는 "Please wait, the character list is being rebuilt."라고 말하고, 목록이 길면 캐릭터 열 개마다 소리 내어 셉니다. 한 서버에는 캐릭터가 많을 수 있지만 게임 화면에는 한 번에 아홉 개만 보입니다. 도구는 캐릭터를 모두 세어 목록에 빠짐없이 넣습니다. 세지 못하면 "The character list may be incomplete. Press Alt F1 twice to rebuild it."이라고 말합니다.

### 서버 변경하기

1. Change server로 가서 Enter를 누릅니다. 도구가 게임의 서버 목록을 열고 화면에서 현재 목록을 읽습니다. 대기 소리와 함께 몇 초가 걸립니다. 끝나면 커서가 첫 서버에 놓입니다. 항목은 먼저 서버들(종류와 서버 상태 포함)이 나오고, 그다음 분류마다 항목이 하나씩 나옵니다. 분류 항목은 게임 서버 목록의 탭이며, "select category"와 탭 이름으로 말합니다. 마지막 항목은 Close server selection입니다. 분류를 고르면 그 탭의 서버들을 읽습니다.
2. 서버를 골라 Enter를 누릅니다. 도구가 "Changing server. Please wait."라고 말한 뒤 "Server changed"와 서버 이름을 말합니다.
3. 도구는 게임이 실제로 어느 서버를 보여 주는지 확인하고, 다른 서버이면 경고합니다: "Attention. The game is on a different server"와 이름. 그곳에서 플레이하기 전에 서버를 다시 변경하십시오.

특수한 경우:

- 아직 캐릭터가 없는 서버에서는 게임이 바로 캐릭터 만들기로 갑니다. 도구가 "No characters on this realm yet."이라고 말합니다.
- 일부 Classic Era 서버는 하드코어나 전쟁 서버 경고를 보여 줍니다. 도구는 그 글을 읽고 "Press Enter to agree, or press Escape to decline."이라고 말합니다. 대신 답하는 일은 절대 없습니다.
- 도구는 서버 대기열을 처리하지 않습니다. 게임이 연결 중 메시지를 보여 주는 동안 도구는 그것을 읽고 기다립니다. 1분쯤 지나면 "The game is still connecting. Press Escape to cancel."이라고 말합니다.
- 게임이 스스로 서버 목록을 열면 "The game has opened the server selection."이 들리고 서버들이 메뉴로 나타납니다. Close server selection이 마지막 항목입니다.
- 게임이 연결 중인 동안(로그인, 서버 변경, 게임 시작) 도구는 버튼이 하나뿐인 팝업을 읽기만 하고 절대 누르지 않습니다. 그 버튼은 "Cancel"이고, 누르면 로그인이 중단되기 때문입니다.

### 캐릭터 만들기

1. Create new character로 가서 오른쪽 화살표를 누릅니다.
2. 성별, 종족, 직업(그 종족이 할 수 있는 직업만 나옵니다), 시작 지역을 차례로 고릅니다. 오른쪽 화살표로 더 들어가고 왼쪽 화살표로 한 단계 돌아갑니다. 시작 지역에서 Enter를 누릅니다.
3. 도구가 "Enter the name for the new character and press enter, or escape to cancel character creation."이라고 말합니다. 이름을 입력하고 Enter를 누릅니다.
4. 게임이 이름을 거부하면 팝업을 보여 줍니다. 도구는 팝업을 소리 내어 읽고, 닫고, 이름 입력란을 비운 뒤 다시 이름을 묻습니다. 다른 이름을 시도하십시오.
5. 성공하면 "Character created"가 들립니다. 도구가 목록을 다시 만들고 주 메뉴로 돌아갑니다. 새 캐릭터가 자동으로 선택되지는 않습니다.
6. 다른 문제가 생기면, 예를 들어 서버에 캐릭터가 이미 최대 개수만큼 있으면, 게임의 팝업을 같은 방식으로 읽어 줍니다. 도구가 18초쯤 아무 응답도 받지 못하면 "Something went wrong. Please restart the game and try again."이 들립니다.

이름 규칙: 공백 없음, 같은 글자 세 번 연속 금지, 첫 글자는 자동으로 대문자.

이름을 입력하는 중에 Escape를 누르면 취소합니다. 도구가 "Creation is canceled. Please wait."라고 말합니다. Classic Era와 TBC에서는 캐릭터의 외형을 고를 수 없습니다. 게임의 기본 외형이 쓰입니다.

하드코어 서버에서는 캐릭터를 만들기 전에 게임이 하드코어 규칙에 동의하라고 합니다. 도구는 규칙을 한 쪽씩 읽고 Enter(동의) 또는 Escape(거절)를 누르라고 합니다.

새 계정에서는 게임이 Blizzard 소셜 규약도 보여 줍니다. 도구가 끝까지 스크롤하고 대신 수락합니다. "Blizzard's social contract is open. Accepting it, please wait."라고 말한 다음 "Social contract accepted."라고 말합니다. 실패하면 비장애인의 도움이 한 번 필요하다는 말이 들립니다. 글을 끝까지 스크롤하고 수락을 누르면 됩니다.

### 캐릭터 삭제하기

1. 먼저 삭제할 캐릭터를 선택합니다("캐릭터를 골라 월드에 들어가기" 참고). 도구는 게임의 삭제 버튼을 쓰므로, 지금 게임에서 선택된 캐릭터를 삭제합니다. 도구가 목록을 센 직후에는 1번 캐릭터가 선택되어 있습니다.
2. Delete character를 골라 Enter를 누릅니다. 도구가 게임의 확인 팝업을 소리 내어 읽습니다. 팝업에 캐릭터 이름이 나오므로 진행하기 전에 이름을 확인하십시오.
3. 도구가 DELETE라는 단어를 대문자로 입력하고 Enter를 누르라고 합니다. 도구가 대신 입력하지는 않습니다. 게임이 받아들이지 않으면 요청을 다시 듣게 됩니다. 취소하려면 Escape를 누르십시오("Deleting is canceled. Please wait"가 들립니다).
4. 성공하면 "Character deleted"가 들리고 목록을 다시 만듭니다.

영어에서 이 단어는 DELETE입니다. 다른 도구 언어에서는 그 언어의 단어입니다(LÖSCHEN, EFFACER, BORRAR, УДАЛИТЬ).

## WoW: Forever에서 도구 쓰기

Forever에서는 도구가 다르게 동작하므로 키가 하는 일도 다릅니다. 게임은 마우스가 머무는 항목을 소리 내어 읽습니다. 도구가 마우스를 대신 움직여 줍니다.

1. 도구가 게임을 알아보면 "Login mode for WoW Forever"와 지역, 언어를 말합니다. 첫 화면들은 게임이 낭독합니다: 스크린리더 질문(도구가 끕니다), 로그인 화면, 규칙 카드, 경험 카드. 도구가 이름을 붙일 수 없는 화면을 만나면 "Forever mode: the game reads the screen itself. Press Control Alt F3 to save a screenshot for calibration."이 들립니다. 버그 보고를 위한 안내입니다. 화살표 키로 계속 진행하십시오.
2. 위아래 화살표는 화면의 다음 항목이나 이전 항목으로 이동합니다. 게임이 각 항목을 말합니다. 목록 끝에서는 커서가 반대쪽 끝으로 돌아갑니다.
3. Page Up과 Page Down은 다섯 항목씩 건너뜁니다. 첫 항목과 마지막 항목에서 멈춥니다.
4. Enter는 항목을 클릭합니다. 텍스트 입력란에서는 Enter가 입력 모드를 시작합니다. "typing mode, Enter or Escape to leave"가 들립니다. 입력한 다음 Enter나 Escape를 누르면 키보드를 도구에 돌려줍니다. Escape는 게임에도 전달됩니다.
5. 왼쪽과 오른쪽 화살표는 외형 옵션의 값을 변경합니다. 다른 항목에서는 왼쪽 화살표가 화면을 다시 읽고 오른쪽 화살표가 현재 항목을 다시 말합니다.
6. Escape는 열린 선택 목록을 닫습니다. 그 밖에는 게임으로 가므로 화면에서 빠져나오거나 게임 메뉴를 엽니다.
7. 도구는 행동 규범(스스로 끝까지 스크롤하고 커서를 Accept에 둡니다), 삭제 대화상자가 있는 캐릭터 목록, Escape로 여는 게임 메뉴도 알아봅니다.
8. Enter World 버튼을 누르면 도구가 Play mode로 변경됩니다. Alt+F1을 누르면 Login mode로 돌아갑니다. 예를 들어 캐릭터 화면으로 돌아갈 때 씁니다.

### Forever에서 캐릭터 만들기

캐릭터 만들기를 모두 지원합니다. 만들기 페이지는 둘입니다.

- 종족과 직업. 종족은 진영별로 나열됩니다. 위아래 화살표로 들을 수 있습니다. 직업 두 줄과 체형으로 모두 이동할 수 있습니다.
- 외형과 이름. 이 페이지에는 전체 이름 입력란, 게임이 보여 주면 두 번째 이름 입력란, 이름 확인, 무작위 이름용 주사위 버튼, 현재 값과 함께 외형 옵션들이 있습니다.

외형 페이지에서 왼쪽과 오른쪽 화살표를 눌러 옵션을 변경합니다. 그러면 도구가 새 값과 번호를 말합니다. 예: "4 of 10". 머리 모양 같은 선택지는 화면에 이름이 나타나면 잠시 뒤 그 이름도 덧붙입니다. 색상 옵션은 게임 안에서 이름이 없습니다. 도구가 대략적인 색 이름을 붙입니다. 예: "light brown". 붉은 기가 도는 밝은 색은 pink라고 부릅니다. 색 이름에는 pale, dull, strong, bright처럼 색의 강도를 나타내는 말이 붙을 수 있습니다.

가장 아래 옵션에서 아래 화살표를 누르면 목록이 더 스크롤됩니다. 도구가 다음 옵션으로 건너뜁니다. 목록이 끝나면 Finish로 넘어갑니다.

이름 확인은 이름 입력란 옆에 작은 아이콘을 보여 줍니다: 초록 체크 표시(사용 가능한 이름), 빨간 X 표시(이유와 함께), 또는 게임이 확인하는 중이거나 입력란이 비어 있으면 아무것도 없음. 도구는 아이콘이 나타내는 것을 말합니다: 이름을 쓸 수 있다는 것, 이름이 거부된 이유, 또는 "no result of the name check yet". 입력한 뒤 결과를 최대 2.5초쯤 기다립니다.

### 항목 반복

게임은 한 번 실행하는 동안 각 문구를 한 번만 말합니다. 이미 들은 항목으로 이동했는데 아무것도 들리지 않으면 도구가 대신 다시 말해 줍니다. 이 반복 기능은 보통 스크린리더 브리지 음성을 쓰면 켜져 있고 실제 음성을 쓰면 꺼져 있습니다. repeatecho 설정으로 이 동작을 변경할 수 있습니다("설정과 파일" 참고).

## 키 목록

Login mode에서, 그리고 처음 설정하는 동안 도구가 다음 키를 받습니다. Play mode에서는 이 키들이 게임으로 갑니다.

| 키 | Classic Era와 TBC | WoW: Forever |
|---|---|---|
| 위 / 아래 화살표 | 이전 또는 다음 메뉴 항목 | 화면의 이전 또는 다음 항목 |
| Page Up / Page Down | 열 항목씩 위나 아래로 이동 | 다섯 항목씩 위나 아래로 이동 |
| 오른쪽 화살표 | 하위 메뉴 열기. 하위 메뉴가 없으면 항목을 다시 말하기 | 외형 옵션의 다음 값. 다른 곳에서는 현재 항목을 다시 말하기 |
| 왼쪽 화살표 | 위 메뉴로 돌아가기 | 외형 옵션의 이전 값. 다른 곳에서는 화면을 다시 읽기 |
| Enter | 항목 실행. 이름과 삭제를 확정하고, 입력란에서는 입력을 끝냄. 하드코어 경고에 동의 | 항목 클릭. 텍스트 입력란에서는 입력을 시작하고 끝내기 |
| Escape | 이름 입력과 삭제를 취소. 입력란에서는 입력을 끝냄. 하드코어 경고를 거절. 그 밖에는 게임으로 감 | 목록 닫기, 입력 끝내기, 또는 게임으로 감 |
| Alt+F1 | Login mode와 Play mode 사이 전환, 진행 중인 동작 멈추기 | Login mode와 Play mode 사이 전환 |
| Alt+Escape | 도구 종료("Terminated"가 들림. 모든 모드에서 동작) | 도구 종료 |
| Ctrl+Alt+F2 | 전체 화면 스크린샷을 Windows 클립보드로 | 같음 |
| Ctrl+Alt+F3 | 개발자용 스크린샷을 도구의 data\captures 폴더에 저장하고 "screenshot saved"라고 말함(버그 보고용) | 개발자용 스크린샷을 도구의 data\captures 폴더에 저장하고 "screenshot saved"라고 말함(버그 보고용) |
| 숫자 키패드 7 | Play mode 전용: 카메라 시점을 맞추고 캐릭터 근처를 오른쪽 클릭 | 같음 |
| 숫자 키패드 8 | Play mode 전용: 카메라 시점을 맞추고 화면 가운데에 조금 더 가까운 곳을 왼쪽 클릭 | 같음 |

숫자 키패드 두 키는 Play mode용 보조 기능이며 WowVision과 함께 쓸 때는 필요 없습니다.

로그인 화면이나 캐릭터 화면에 머무는 동안에는 Alt+F1로 도구를 꺼 둘 수 없습니다. 도구가 1~2초 안에 그 화면을 다시 알아보고 Login mode로 돌아갑니다. 도구를 정말로 멈추려면 Alt+Escape를 누르거나 게임 창에서 벗어나십시오(Alt+Tab). 그러면 도구는 Pause mode에 머뭅니다.

## 음성과 낭독

- 도구는 스크린리더가 아니라 Windows 음성(SAPI)으로 말합니다. 음성은 처음 시작할 때의 설정에서 고르거나 나중에 Select voice로 고릅니다. 도구는 음성을 먼저 소리 없이 시험해 봅니다. 음성이 동작하지 않으면 "This voice does not work, choose another one"이 들리고 기존 음성이 유지됩니다.
- 음성 목록이 비어 있으면 "No voices found, press Enter to keep the system voice."가 들립니다.
- 특별 항목 SAPI2SR은 실제 음성이 아닙니다. 글을 NVDA에 넘겨주는 브리지라서, 자신의 스크린리더 음성으로 듣게 됩니다. 이 음성을 쓰면 화살표 키가 NVDA의 말을 끊습니다. 실제 음성을 쓰면 평소처럼 이동할 때마다 말이 끊깁니다.
- Forever에서 낭독 음성은 고른 음성이 Windows 음성 목록에서 몇 번째인지로 정해집니다. 말하기 속도는 기본 5입니다. "설정과 파일"을 보십시오. Forever에서 엉뚱한 음성이 들리면 forever.ini에서 voice=를 설정하십시오. 도구의 로그에 모든 음성과 번호가 나와 있습니다.
- 출력 장치는 설정 파일의 gAudioOutputMatch로 변경할 수 있습니다. 장치 이름의 일부를 입력합니다. 비워 두면 시스템 기본값입니다.

## 설정과 파일

도구의 파일은 WoW Login Tool 폴더에 있습니다. 작은 텍스트 파일입니다. 도구를 닫은 상태에서 편집하십시오.

| 파일 | 담긴 내용 |
|---|---|
| data\settings.ini | 설정 내용: 게임 종류(직접 골랐는지 여부 포함), 음성, 언어, 지역, 출력 장치. 처음 시작할 때의 설정을 다시 하려면 도구를 닫은 상태에서 이 파일을 삭제하십시오. |
| data\forever.ini | Forever 옵션: voice=(Windows 음성의 번호, 0부터 셈), rate=(-10~10, 0이 보통), volume=(0~100), repeatecho=(1 또는 0), echo=(1이면 도구가 모든 항목을 말함, 디버깅용), wheelnext=up(게임 목록이 반대로 스크롤되면 마우스 휠 단계의 방향을 뒤집음). voice 줄이 없으면 Forever는 도구에서 고른 음성을 씁니다. |
| log.txt | 현재 실행의 로그. 최근 다섯 번의 실행은 log-1.txt부터 log-5.txt로 보관됩니다. |

### 도구가 게임에 쓰는 것

Forever에서는 게임이 닫혀 있는 동안 도구가 게임 설정에 낭독 설정을 써 넣어, 게임이 내 음성으로 말하게 합니다.

## 팁

- Battle.net 앱으로 로그인하십시오. 이 앱은 Windows와 Mac 모두에서 스크린리더로 쓸 수 있습니다. "keep me logged in"을 한 번 체크해 두십시오. 그러면 게임이 저절로 로그인하고, 도구는 서버와 캐릭터 화면에서 시작합니다.
- 이 페이지의 안내는 다른 기기에서 읽으십시오. 게임 창이 초점을 잃을 때마다 도구가 일시 정지하고, 돌아오면 주 메뉴에서 다시 시작합니다.
- 캐릭터를 만들거나 삭제한 뒤에는 캐릭터 목록을 다시 들으십시오. 목록을 다시 만들므로 번호가 변경될 수 있습니다.
- 느긋하게 기다리십시오. 서버 목록과 캐릭터 세기는 몇 초가 걸립니다. 도구는 작업하는 동안 대기 소리를 냅니다.
- Classic Era와 TBC에서는 오버레이와 색 변경을 끄십시오(문제 해결 참고).
- "Play mode"가 들리고 월드가 로드되면 WowVision이 맡습니다. WowVision에서 아무 소리도 들리지 않으면 [문제 해결](troubleshooting.md)을 확인하십시오.

## WowVision과 로그인 도구가 함께 동작하는 방식

도구의 역할은 캐릭터가 월드에 들어서면 끝납니다. Play mode에서는 화면을 지켜보기만 하고 숫자 키패드 카메라 보조 기능 두 개를 제공합니다. 그때부터는 모두 WowVision이 맡습니다([빠른 시작](quick-start.md) 참고).

- 도구는 WowVision이 필요 없고 WowVision도 도구가 필요 없습니다.
- 플레이하는 동안 도구를 백그라운드에서 계속 실행해 두어도 됩니다. 끄고 싶으면 Alt+Escape를 누르십시오.
- 로그아웃한 뒤처럼 캐릭터 화면으로 돌아오면 이 페이지의 처음부터 다시 시작하십시오. Forever에서는 Alt+F1을 눌러 Login mode로 돌아가십시오.
- WowVision은 Sku 애드온을 선택 애드온으로 나열하지만, 로그인 도구와는 연동하지 않습니다. Sku 애드온이 로드되어 있으면 WowVision은 둘이 키를 두고 다투지 않도록 일부 키, 창, 명령을 끕니다. 예를 들어 주시 대상 키, 소프트 대상 지정, 툴팁 줄 키(Shift+Up, Shift+Down, Shift+Left, Shift+Right), 그리고 대화, 거래, 우편, 상급자 같은 창입니다. 이때 /pquit, /dquit, /focus1부터 /focus5까지의 명령은 Sku에 맡깁니다.
- WowVision이 모든 것을 맡게 하려면 /disableaddon sku 명령으로 Sku와 Sku의 오디오, 사운드 팩을 끄고 인터페이스를 다시 불러옵니다. /enableaddon sku를 입력하면 다시 켜집니다. BlindSlash가 로드되어 있으면 이 두 명령은 없습니다.

WowVision이 Sku에 맡기는 창, 키, 명령의 전체 목록은 [WowVision과 Sku 함께 쓰기](sku.md)에 있습니다.

## 문제 해결

| 문제 | 해 볼 것 |
|---|---|
| 게임이 열려 있는데 도구가 Pause mode에 머물며 아무 말도 하지 않음 | 도구는 게임 창에 초점이 있을 때만, 그리고 게임 창을 알아본 뒤에만 동작합니다. 게임 창 안을 클릭하십시오. 어떤 컴퓨터에서는 게임을 먼저 시작하고 도구를 나중에 시작하는 편이 더 잘 됩니다. 아무것도 효과가 없으면 도구와 게임을 다시 시작하십시오. |
| "Unknown screen. Close the dialog in the game, then press Alt F1 twice." | 게임이 도구가 모르는 화면을 보여 주고 있습니다. 대개 게임 메뉴나 대화상자입니다. Escape로 닫은 다음 Alt+F1을 두 번 누르십시오. |
| "The screen recognition textures are missing from the game folder" | 다섯 텍스처 폴더를 다시 복사하십시오("받아서 설치하기" 참고). |
| 도구가 어떤 화면도 알아보지 못함 | Discord 게임 내 오버레이를 끄십시오(User Settings, Game Overlay). Nvidia 오버레이는 Alt+R로 숨기십시오. Windows와 게임에서 HDR, 고대비, 밝기, 색 필터를 원래대로 되돌리십시오. |
| "The game is starting. Please wait."가 오래 계속됨 | 게임이 아직 로딩 중입니다. 도구는 아무것도 알아보지 못한 채 12초쯤 지나야 "Unknown screen"이라고 말합니다. |
| "Something went wrong. Please restart the game and try again." | 동작이 실패했습니다. 도구가 삐 소리를 두 번 내고 Pause mode로 들어간 뒤, 스스로 화면을 다시 알아봅니다. Alt+F1을 눌러 진행 중인 동작을 멈추고 다시 시도하십시오. 계속 이러면 게임과 도구를 다시 시작하십시오. |
| 계정 화면에서 "Not logged in" | Account name, Password, Log in을 쓰거나, Battle.net과 게임을 다시 시작하십시오. |
| "The server list did not load. Please try again." | 읽을 때 서버 목록이 비어 있었습니다. 몇 초 기다린 뒤 Change server를 다시 여십시오. |
| 이름, 서버, 팝업을 잘못 읽거나 엉뚱한 말로 읽음 | 도구에 설정한 언어가 게임 클라이언트의 언어와 맞지 않을 가능성이 큽니다. 도구는 그 언어로 화면을 읽습니다. Select language로 변경하십시오. |
| Forever에서 게임의 기본 음성이 들림 | 도구가 낭독 설정을 써 넣을 수 있도록 게임을 닫고, 도구를 시작한 다음 게임을 시작하십시오. |
| 도구가 조용하거나 "This voice does not work"라고 말함 | Select voice에서 다른 음성을 고르십시오. 어떤 음성도 동작하지 않으면 Windows 음성 설정을 확인하십시오. |
| Forever에서 반복 항목이 들리지 않음 | forever.ini에서 repeatecho=1로 설정하고 도구를 다시 시작하십시오. |
| 그래도 무언가 잘못됨 | 로그를 챙기십시오. 도구 자체의 로그는 도구 폴더의 log.txt 파일입니다. 로그와 도구 버전(도구가 시작할 때 말합니다)을 함께 WowVision Discord에 보고하십시오. |

## 알려진 한계

- Classic Era와 TBC에서는 외형 옵션을 쓸 수 없습니다.
- Forever에서 긴 목록(예: 머리 모양)을 아주 빠르게 변경하면 도구가 바로잡기 전에 잠깐 엉뚱한 값을 말할 수 있습니다.
- 도구를 쓰려면 Windows PC가 필요합니다. Mac 버전이 있지만 여기서는 다루지 않습니다.
- 첫 로그인 전의 라이선스 문서에는 여전히 비장애인의 도움이 한 번 필요합니다. 게임 안의 소셜 규약은 도구가 처리합니다.

## 출처

- [WoW Login Tool 버전 4 다운로드(WoW-Login-Tool.zip이 있는 "login-tool" 릴리스)](https://github.com/Sku75/Sku-WoW-Addon-TBC/releases/tag/login-tool)
- [도움을 받을 수 있는 Sku Discord 초대 링크](https://discord.gg/AzFwTDmpbk)

함께 보기: [설치](installation.md), [빠른 시작](quick-start.md), [문제 해결](troubleshooting.md).
