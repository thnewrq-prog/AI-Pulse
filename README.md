<div align="center">

# AI Pulse

### Your AI usage. One clear view.

Track usage limits, remaining credits, and Fast GPU time across your AI services — from your browser or Windows tray.

**Windows tray + Chrome / Edge 118+** · **7 built-in services + custom services** · **v1.13.5**

[**Download v1.13.5 ↓**](./AI-Pulse-v1.13.5.zip?raw=true) · [What’s new / 업데이트](#whats-new) · [Installation](#installation) · [한국어 안내](#korean-guide) · [Full changelog](./CHANGELOG.md)

</div>

---

## 📑 Contents

1. [✨ v1.13.5 updates / 업데이트](#whats-new)
2. [💻 Overview](#overview)
3. [🚀 Features](#features)
4. [🤖 Supported services](#supported-services)
5. [📦 Installation](#installation)
6. [▶️ Quick start](#quick-start)
7. [🔄 Updating](#updating)
8. [🔐 Privacy & permissions](#privacy--permissions)
9. [🛠️ Troubleshooting](#troubleshooting)
10. [🇰🇷 한국어 안내](#korean-guide)

<a id="whats-new"></a>

## ✨ v1.13.5 updates / 업데이트

> **v1.13.5 팝업 안내 수정 배포:** 트레이 하단의 응답 지연 문구가 계속 남는 문제를 수정했습니다. 안내는 6초 뒤 또는 정상 응답 수신 시 해제되며, 정상 상태를 받은 뒤 발생하던 초기 읽기 시간 초과도 방지합니다. 다운로드 ZIP은 수정 파일을 포함한 전체 설치 패키지입니다. 기존 트레이·브라우저를 종료하고 설치기를 다시 실행한 뒤 확장을 새로고침하세요. 버전은 1.13.5로 유지됩니다.

**v1.8.0 대비 누적 변경 사항**입니다. 기존 사용자 정의 서비스·10종 프리셋·잔액 위치 지정·한국어/영어 지원은 유지됩니다.

| 구분 | 추가·수정 내용 |
| --- | --- |
| Windows 트레이 | 확장과 연결된 트레이 팝업에서 사용량 확인·전체/개별 갱신·대시보드 열기 |
| 초기화 알림 | 서비스별 매주·매월·일회성 일정을 직접 설정하고 24시간 이내에 회차당 한 번 알림; 테스트 알림 추가 |
| 트레이 중복 수정 | 여러 브라우저·프로필의 연결을 유지하면서 표시 아이콘은 하나로 조정; 연결 서비스 수 우선, 동률 유지, 종료 시 승계 |
| Suno·계정 연결 | 잔액 판독과 로그인 확인을 분리; Suno 활성 세션·중복 로그아웃 문구·늦은 화면 갱신 감지 보완 |
| Gemini 조회 | 사용량 팝오버의 세션/주간 한도 인식, 한국어 문구·메뉴 탐색 및 숨김 페이지 대기 개선 |
| 서비스 바로가기 | 팝업 서비스 아이콘으로 메인 화면 열기; 키보드 및 동작 줄이기 지원 |
| 설치·Edge 등록 | MSI 기반 설치와 Native Messaging 등록; Edge 개발자 모드·로드 버튼·폴더 확인·진단 로그 보완 |
| 프리셋 | Magnific 구독 화면·BytePlus Lumina 요금제 화면으로 기본 주소 수정 |

**중요한 동작 변경:** debugger 권한을 제거하고 nativeMessaging·alarms·notifications를 추가했습니다. 자동 조회는 트레이 연결과 창 숨김 확인이 필요합니다. v1.8.0의 ComfyUI 공식 응답 캡처 경로는 비활성화되어 화면 판독/잔액 위치 지정을 사용합니다. 기본 서비스의 사이트 접근 권한은 설치 시 선언되며 추가 서비스는 선택적 권한을 사용합니다.

**English:** Since v1.8.0, this release adds a Windows tray companion, scheduled reset reminders and test notifications, service-home shortcuts, MSI installation, and more specific Gemini collection. It fixes duplicate tray ownership and improves Suno/account-connect completion detection and Edge registration. Magnific/Lumina preset URLs are updated. Background refresh now requires the native tray connection; debugger-based ComfyUI response capture is no longer active.

[**상세 변경·버그 수정·권한 비교·검증 범위 / Full changelog →**](./CHANGELOG.md)

<a id="overview"></a>

## 💻 Overview

AI Pulse brings official website usage and balances into a compact browser popup, a customizable dashboard, and a Windows tray popup. Sign in on each service’s official website, refresh AI Pulse, and view the latest available values and last checked time.

Collection depends on the website, login state, and account. Results are snapshots, not a continuous live feed. API token usage and API billing are not tracked. End-to-end operation across all real services/accounts has not been verified in this comparison.

<a id="features"></a>

## 🚀 Features

- **Popup, dashboard & tray:** View balances and usage, refresh services, and open the dashboard or service home pages.
- **Custom services:** Use 10 presets or your own service URL, name, color, symbol, and credit/GPU-time type. Presets are form defaults, not dedicated API integrations.
- **Balance picker:** Hover preview, multiple-number selection, parent selection, and recorded menu-opening clicks.
- **Concurrent refresh:** Refresh connected visible services together after a 1.5-second notice. Hidden cards are excluded. The native companion must confirm hiding the lookup window before collection starts.
- **Reset reminders:** Configure schedules yourself, including weekly/monthly/one-time resets; notifications occur within 24 hours before a reset, once per cycle. Browser execution and notification permission are required.
- **Local preferences:** Store connections, layout, snapshots, and refresh history in the browser. The tray receives local state through Native Messaging; it does not merge browser profiles.
- **Korean / English:** Switch the existing dashboard and popup language in Settings or the top bar. New desktop/notification controls may include Korean text.

<a id="supported-services"></a>

## 🤖 Supported services

| Service | Official-page information |
| --- | --- |
| Google Gemini | Available session and weekly usage |
| Claude | Session and weekly usage |
| ChatGPT | Explicit quota values available on the Usage screen |
| ComfyUI Cloud | Credit balance through screen reading/balance binding |
| Midjourney | Fast GPU time |
| Suno | Remaining credits |
| Higgsfield | Remaining credits |

Custom presets: Magnific, Lumina, Dreamina, Kling AI, Hailuo AI, OpenArt, Runway, Leonardo.Ai, ElevenLabs, Luma Dream Machine. Readable values vary by account and layout; balance binding may be required.

<a id="installation"></a>

## 📦 Installation

**Requirements:** Windows, Chrome or Microsoft Edge 118+, and WebView2 Runtime for the tray popup. Browser/organization policies may restrict unpacked extensions or native applications.

1. [Download AI-Pulse-v1.13.5.zip](./AI-Pulse-v1.13.5.zip?raw=true) and extract it.
2. Exit any existing AI Pulse tray instances and close the relevant browsers.
3. Run **AI-Pulse-설치.exe** to install the extension and tray companion. Review any system/permission prompts yourself.
4. In the AI Pulse start screen, select Chrome or Edge to register the extension. Leave the browser and folder selection dialog alone while setup runs.
5. Restart the browser and verify **1.13.5** in its extension manager. Reload if needed.

| Browser | Extension manager |
| --- | --- |
| Chrome | chrome://extensions |
| Edge | edge://extensions |

The ZIP contains an installer, not a top-level AI-Pulse extension folder. The default installed folder is **%LOCALAPPDATA%\AIPulse**, with the extension in **AI-Pulse** below it. If automatic registration fails, inspect the setup log at **%LOCALAPPDATA%\AI Pulse Setup\browser-setup-*.log** and follow the start-screen instructions. Managed-policy restrictions are not bypassed.

The installer is unsigned. This release has not been verified to resolve previous antivirus detections; no antivirus clearance is claimed.

<a id="quick-start"></a>

## ▶️ Quick start

1. Open AI Pulse from the extension icon or Windows tray.
2. Open the dashboard, connect a service, and sign in directly on its official website.
3. AI Pulse may close the Account Connect tab after confirming sign-in. Regular tabs, manually opened official pages, authentication screens, and active balance picking are preserved.
4. Click Refresh All or refresh an individual service. Keep the browser and tray connection running.
5. For reset reminders, open Settings → Windows tray / reset notifications, enable the service, choose its schedule, and save. Use the test-notification button to request a preview.

<a id="updating"></a>

## 🔄 Updating

Exit **all** old AI Pulse tray icons and browsers, run the new installer, restart/register the browser, and verify version 1.13.5. Older running processes do not participate in the new single-tray coordination.

Before migrating from v1.8.0, export any history you need to retain. v1.13.5 introduces a manifest public key and a new installation location, so automatic transfer of the old extension’s connections, layout, and history is not guaranteed. History export is not a full settings backup/import feature. Verify your connections after installation.

Older download: [v1.8.0](./AI-Pulse-v1.8.0.zip?raw=true). Its update notes remain in [CHANGELOG.md](./CHANGELOG.md).

<a id="privacy--permissions"></a>

## 🔐 Privacy & permissions

- **Official sign-in:** Sign in on each service’s own website. Suno’s active-session probe returns only a boolean, not identifiers, tokens, or cookies.
- **Local state & tray:** Browser settings and collected values are shared locally with the installed native companion to render the tray. Profiles keep separate data.
- **Permissions:** v1.13.5 uses storage, scripting, nativeMessaging, alarms, and notifications. The debugger permission used in v1.8.0 is removed.
- **Site access:** Built-in service domains plus Magnific/BytePlus are declared in host_permissions. Other custom sites use optional HTTP/HTTPS access requested when connecting.
- **Lookup windows:** Created by AI Pulse, hidden after native confirmation, and cleaned up afterward. A brief taskbar appearance is possible; hidden-site restrictions may still cause collection failures.

<a id="troubleshooting"></a>

## 🛠️ Troubleshooting

| Problem | Try this |
| --- | --- |
| Duplicate tray icons after updating | Exit all old tray instances and browsers, then restart; old processes do not coordinate with the new version. |
| Background refresh cannot start | Check the native tray connection in Settings; refresh stops if hiding cannot be confirmed. |
| Account Connect page stays open | Complete authentication; the page is kept if sign-in cannot be confirmed. Suno detection retries within the watch period. |
| Credits are missing | Open the official page and use Bind Balance / Read Current Page. ComfyUI response capture from v1.8.0 is inactive. |
| Notification request succeeds but no banner appears | Check Win+N, Windows browser-notification permission, and Do Not Disturb/Focus settings. API acceptance is not proof of visible delivery. |
| Edge registration fails | Review the setup diagnostic log and organization policy; full registration was not tested here. |

[Report an issue](https://github.com/thnewrq-prog/AI-Pulse/issues) with the version, service, and error message. Remove personal details from screenshots/logs.

<a id="korean-guide"></a>

## 🇰🇷 한국어 안내

**설치:** ZIP 압축 해제 → 기존 트레이 모두 종료·브라우저 닫기 → **AI-Pulse-설치.exe** 실행 → 시작 화면에서 Chrome/Edge 선택 → 브라우저 재시작 → 확장 버전 **1.13.5** 확인.

**사용:** 확장 또는 트레이 팝업 → 대시보드 → 계정 연결 → 공식 사이트 로그인 → 전체/개별 갱신. 서비스 아이콘을 누르면 메인 화면을 엽니다. 알림은 설정에서 초기화 일정을 직접 입력하고 저장합니다.

**알아두세요:** 자동 갱신에는 트레이 연결이 필요합니다. 일반 탭·인증 입력·잔액 위치 지정 화면은 자동 정리하지 않습니다. v1.8.0의 설정·기록 자동 이전은 보장되지 않으므로 필요한 기록을 먼저 내보내세요. 설치 파일은 디지털 서명이 없으며 이전 백신 차단의 해결 여부를 검증한 배포판은 아닙니다.

**검증:** 이번 비교에서 실제 MSI 파일을 정적 추출하고 확장 JavaScript 구문 검사와 로그인 모의 회귀 테스트 **81개**를 통과했습니다. 실제 설치·트레이 표시·로그인 계정 조회·알림 배너·Edge 자동 등록 전체 과정은 실행하지 않았습니다. 배포 문서가 보고한 다른 검사와 상세 변경 사항은 [업데이트 기록](./CHANGELOG.md)을 확인하세요.
