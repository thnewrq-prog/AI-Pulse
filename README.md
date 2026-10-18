# AI Pulse

**A Chrome and Edge extension that brings your AI usage and remaining credits into one dashboard.**

Sign in on each service’s official website, then refresh AI Pulse to check the available usage information.

## Supported Services

| Service | Information |
|---|---|
| Google Gemini | Usage percentages and limits shown on the official website |
| Claude | Session and weekly usage shown on the official website |
| ChatGPT | Usage percentages and limits available on the official website |
| ComfyUI Cloud | Remaining credits |
| Midjourney | Included and purchased/awarded Fast time |
| Suno | Remaining credits |
| Higgsfield | Remaining credits |

Available information varies by service and account. AI Pulse does not track API token usage or API billing.

## Features

- **Quick-view popup** — Check service usage from the extension icon.
- **Refresh all or individually** — Refresh All starts automatically after a 1.5-second notice.
- **Concurrent checks** — Check all connected, visible services at once.
- **Background checks** — Run checks without switching focus away from your work.
- **Customizable dashboard** — Reorder cards and hide or show services.
- **Local storage** — Keep connection settings, dashboard preferences, results, and history in your browser.
- **Dark theme** — Black backgrounds with neon green accents.

## Installation

Requires **Chrome or Edge 118 or later**.

1. Select **Code → Download ZIP** in this repository and extract the archive.
2. Open your browser’s extension management page:
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
3. Enable **Developer mode**.
4. Click **Load unpacked**.
5. Select the **AI-Pulse folder containing `manifest.json`**.
6. Pin AI Pulse to your browser toolbar for easy access.

## How to Use

1. Click the extension icon, then **새 탭 열기** (Open in New Tab).
2. Click **계정 연결** (Connect Account) for a service.
3. Sign in directly on the service’s official website.
4. Return to AI Pulse and click **전체 갱신** (Refresh All) or the service’s refresh button.
5. Check the usage, remaining balance, and last checked time.

If your login session remains valid in the same browser profile, you can refresh again after restarting your browser or computer. Expired sessions require signing in again.

> The current interface is primarily in Korean.

## Updating

1. Download the latest version and overwrite the files in your existing **AI-Pulse folder**.
2. Open your browser’s extension management page and click **Reload** for AI Pulse.
3. Close and reopen the dashboard tab.

## Permissions and Privacy

- You sign in on official service websites. AI Pulse does not collect or store passwords, cookies, or authentication tokens.
- Connection settings and results stay in your browser. AI Pulse does not send them to a separate server.
- The **`debugger` permission** helps keep background lookup pages active when they are covered or minimized.
- This permission grants broad capabilities. AI Pulse uses it on automatically created lookup tabs to maintain page activity and read ComfyUI’s official balance response.
- Your browser may display a **debugging notification** during checks. AI Pulse disconnects and closes its lookup windows when the check finishes.

## Limitations

- Displayed values are snapshots from the **last refresh**, not a continuously updating live feed.
- Lookup windows are minimized and may appear in your taskbar.
- Website changes, expired sessions, security checks, and network conditions can cause checks to fail.
- Version 1.6.1 has passed simulated and reproduced-screen tests, but operation is not guaranteed across all services and real accounts.
- If a check fails, open the official website and verify your login status. Credit services also support **잔액 위치 지정** (Select Balance Location), and the account connection page offers **수동 화면 읽기** (Read Current Page).

When reporting an issue, include the **service name, extension version, and error message**.

|---|---|
|---|---|

# AI Pulse

**여러 AI 서비스의 사용량과 남은 크레딧을 한곳에서 확인하는 Chrome·Edge 확장 프로그램입니다.**

각 서비스의 공식 웹사이트에 로그인한 뒤, AI Pulse에서 갱신 버튼을 눌러 사용량을 확인할 수 있습니다.

## 지원 서비스

| 서비스 | 확인 항목 |
|---|---|
| Google Gemini | 공식 화면에 표시되는 사용률·한도 |
| Claude | 공식 화면에 표시되는 세션·주간 사용률 |
| ChatGPT | 공식 화면에서 제공하는 사용률·한도 |
| ComfyUI Cloud | 남은 크레딧 |
| Midjourney | 구독 및 구매·지급 Fast 시간 |
| Suno | 남은 크레딧 |
| Higgsfield | 남은 크레딧 |

※ 서비스와 계정에 따라 제공되는 항목이 다릅니다. API 토큰 사용량이나 API 청구 금액을 조회하는 프로그램은 아닙니다.

## 주요 기능

- **빠른 보기 팝업**: 확장 아이콘을 눌러 서비스별 사용량 확인
- **전체·개별 갱신**: 전체 갱신은 안내 후 1.5초 뒤 자동 시작
- **동시 조회**: 표시 중인 연결 서비스를 동시에 확인
- **백그라운드 조회**: 작업 창의 포커스를 바꾸지 않고 조회 진행
- **대시보드 편집**: 카드 순서 변경, 서비스 숨기기·다시 표시
- **로컬 저장**: 연결 설정, 표시 순서, 조회 결과와 기록을 브라우저에 보관
- **다크 테마**: 블랙 바탕과 네온 초록 포인트 적용

## 설치 방법

**Chrome 또는 Edge 118 이상**이 필요합니다.

1. 저장소의 **Code → Download ZIP**을 누르고 압축을 풉니다.
2. 브라우저에서 확장 프로그램 관리 페이지를 엽니다.
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
3. **개발자 모드**를 켭니다.
4. **압축해제된 확장 프로그램 로드**를 누릅니다.
5. `manifest.json`이 들어 있는 **AI-Pulse 폴더**를 선택합니다.
6. 도구 모음에 AI Pulse 아이콘을 고정하면 편리합니다.

## 사용 방법

1. 확장 아이콘을 누르고 **새 탭 열기**로 대시보드를 엽니다.
2. 사용할 서비스의 **계정 연결**을 누릅니다.
3. 해당 서비스의 공식 페이지에서 직접 로그인합니다.
4. AI Pulse로 돌아와 **전체 갱신** 또는 서비스별 **갱신**을 누릅니다.
5. 조회가 끝나면 사용량·잔액과 조회 시각을 확인합니다.

같은 브라우저 프로필에서 로그인 상태가 유지되면, PC나 브라우저를 다시 켠 뒤에도 갱신 버튼으로 조회할 수 있습니다. 로그인 세션이 만료되면 다시 로그인해야 합니다.

## 업데이트 방법

1. 새 버전의 파일을 기존 **AI-Pulse 폴더에 덮어씁니다**.
2. 확장 프로그램 관리 페이지에서 AI Pulse의 **새로고침**을 누릅니다.
3. 기존 대시보드 탭을 닫고 다시 엽니다.

## 권한 및 개인정보

- 공식 사이트에서 로그인하며, 비밀번호·쿠키·인증 토큰을 수집하거나 저장하지 않습니다.
- 연결 설정과 조회 결과는 이 브라우저에 저장하며, 별도 서버로 전송하지 않습니다.
- 가려진 조회 페이지의 실행을 유지하기 위해 **디버깅 권한(`debugger`)**을 사용합니다.
- 디버깅 권한은 광범위한 기능을 허용하지만, 이 프로그램에서는 자동 생성한 조회 탭의 실행 유지와 ComfyUI 공식 잔액 응답 확인에 사용합니다.
- 조회 중 브라우저에 **디버깅 중** 표시가 나타날 수 있습니다. 조회가 끝나면 연결을 해제하고 조회 창을 닫습니다.

## 알아두세요

- 표시값은 **마지막 갱신 시점의 조회 결과**입니다. 계속 자동으로 갱신되는 실시간 수치는 아닙니다.
- 조회 창은 최소화되며 작업 표시줄에 나타날 수 있습니다.
- 사이트 화면 변경, 로그인 만료, 보안 확인, 네트워크 상태에 따라 조회가 실패할 수 있습니다.
- v1.6.1은 재현·모의 검사를 거쳤지만, 모든 서비스와 실제 계정에서의 동작을 보장하지 않습니다.
- 조회가 안 되면 공식 화면에서 로그인 상태를 확인하세요. 크레딧 서비스는 **잔액 위치 지정**, 계정 연결 화면에서는 **수동 화면 읽기**도 사용할 수 있습니다.

문제를 제보할 때는 **서비스 이름, 확장 프로그램 버전, 오류 문구**를 함께 남겨 주세요.
