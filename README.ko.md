# DeskPin 🦀☁️

[English](README.md) · 한국어

**macOS 바탕화면에 사는 픽셀 캐릭터 위젯이자 앱 런처.**

Claude Code 마스코트 Clawd(주황 게)와 Codex 짝꿍 Cody(남색 구름)가 바탕화면 위, 일반 창 아래에서 출근·타자·꾸벅·퇴근을 반복합니다. 캐릭터를 누르면 연결된 앱(`Claude.app` / `Codex.app`)이 열립니다.

> [!NOTE]
> macOS 26 이상, Apple Silicon 전용입니다. 실행 파일은 배포하지 않으며 직접 빌드해서 씁니다. 공증되지 않은 ad-hoc 서명이라 다른 Mac으로 옮기면 Gatekeeper가 막을 수 있습니다.

## 빌드와 실행

Xcode 없이 Command Line Tools의 `swiftc`로 빌드합니다.

```sh
git clone https://github.com/tinkerer0/desk_pin.git
cd desk_pin
./build.sh          # 빌드 → ad-hoc 서명 → /Applications/DeskPin.app 설치
open -a DeskPin
```

움직임 위젯(탐정·저글링·춤 등)에 쓰는 스프라이트 그림은 저장소에 들어 있지 않습니다. 그림이 없어도 빌드는 되지만 그 위젯들은 비어 보일 수 있습니다. 기본 위젯인 Clawd 집·Cody 집은 코드로 그려서 그림 없이 동작합니다.

## 사용법

| 동작 | 결과 |
| --- | --- |
| 좌클릭 | 연결된 앱 실행 |
| 끌기 | 위치 이동 (자동 저장) |
| 가장자리 끌기 | 크기 조절 |
| 우클릭 | 숨기기 · 크기 초기화 · 위젯 켜고 끄기 · 애니메이션 · 로그인 시 자동 시작 · 종료 |

메뉴 막대의 픽셀 게 아이콘에서도 같은 메뉴를 쓸 수 있습니다.

## 저장과 네트워크

- 위젯 위치·크기·설정은 `~/Library/Application Support/DeskPin/config.json`에 저장하고, 실행 기록은 `/tmp/deskpin.log`에 남깁니다.
- 네트워크를 쓰지 않습니다. 클릭하면 이 Mac에 있는 앱을 열 뿐입니다.
- 창이 가려져 있으면 그리기를 건너뛰어 전력을 아낍니다.

## Feedback

제가 이런 분야를 접한 지 얼마 안 돼서 부족한 점이 많습니다. 고칠 점이나 알려주실 내용이 있다면 issue나 PR로 남겨주시면 너무 감사하겠습니다.

I am still new to this, so there is a lot to improve. Issues and pull requests with fixes or suggestions are very welcome.

## License

코드는 [MIT](LICENSE)입니다.

Clawd 캐릭터 디자인은 Anthropic의 것(© Anthropic)이고, Cody는 Clawd를 바탕으로 만든 캐릭터라 둘 다 이 라이선스에 포함되지 않습니다. 이 앱은 Anthropic·OpenAI와 관계없는 개인 프로젝트입니다.
