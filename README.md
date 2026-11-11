# DeskPin

English · [한국어](README.ko.md)

**A pixel-character widget and app launcher that lives on the macOS desktop.**

Clawd (the orange crab, Claude Code's mascot) and Cody (the navy cloud, Clawd's Codex companion) sit on the desktop, below regular windows, and repeat a loop of arriving at work, typing, nodding off, and leaving. Click a character to open its linked app (`Claude.app` / `Codex.app`).

> [!NOTE]
> Requires macOS 26 or later and Apple Silicon. No executable is distributed; you build it yourself. The app is signed ad hoc and not notarized, so Gatekeeper may block it if you move it to another Mac.

## Build and run

It builds with `swiftc` from the Command Line Tools, without Xcode.

```sh
git clone https://github.com/tinkerer0/desk_pin.git
cd desk_pin
./build.sh          # build → ad-hoc sign → install to /Applications/DeskPin.app
open -a DeskPin
```

The sprite artwork used by the animated widgets (detective, juggling, dance, and so on) is not included in the repository. The build succeeds without it, but those widgets may look empty. The default widgets, Clawd's house and Cody's house, are drawn in code and work without the artwork.

## Usage

| Action | Result |
| --- | --- |
| Left-click | Opens the linked app |
| Drag | Moves the widget (position is saved automatically) |
| Drag an edge | Resizes the widget |
| Right-click | Hide (숨기기) · Reset size (크기 초기화) · Turn widgets on or off (위젯 켜고 끄기) · Animation (애니메이션) · Start at login (로그인 시 자동 시작) · Quit (종료) |

The same menu is available from the pixel crab icon in the menu bar.

## Storage and network

- Widget positions, sizes, and settings are stored in `~/Library/Application Support/DeskPin/config.json`, and the run log is written to `/tmp/deskpin.log`.
- It does not use the network. A click only opens an app that is already on this Mac.
- When the window is covered, it skips drawing to save power.

## Feedback

I am new to this field and there is a lot I still get wrong. If you see something to fix or something I should know, an issue or PR would be very much appreciated.

## License

The code is under the [MIT](LICENSE) license.

The Clawd character design belongs to Anthropic (© Anthropic), and Cody is a character made based on Clawd, so neither is covered by this license. This app is a personal project and is not affiliated with Anthropic or OpenAI.
