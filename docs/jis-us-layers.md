# JIS-US レイヤー（Cygnus マニュアル p.15–16）

ZMK / Studio は **US 配列の Output** を送る。OS が **日本語 JIS 106** のとき、押下結果はマニュアル **「JIS Keyboard」列** になる。

JP リポでは **Mac 側は US Output のまま**（`mac_num` / `mac_symbol`）、**Windows 側**（`win_num` / `win_symbol`）だけ、**同じ物理位置で Mac と同じ文字**が出るよう Output を差し替える。

## レイヤー

| # | Win (BT0) | Mac (BT1/2) |
|---|-----------|-------------|
| 2 | `win_num` | `mac_num` (10) |
| 3 | `win_symbol` | `mac_symbol` (9) |

入口: `win_base` → `WIN_NUM` / `WIN_SYMBOL`、`mac_base` → `MAC_NUM` / `MAC_SYMBOL`。

## `win_base`（L の右隣）

Mac と同じ **タップで `-`**・長押しでスクロール層。JIS OS では Output **`MINUS`**（`SEMICOLON` だと `;` になるだけで `-` は出ない）。

## 変換の読み方（マニュアル Shift 表）

「JIS で **この文字** を出したい」とき、表の **Shift + ○○（US 側のキー名）** に相当する ZMK Output を送る。

| 出したい文字 | win 側 Output（例） |
|--------------|---------------------|
| `!` `?` | `EXCLAMATION` / `QUESTION` |
| `@` | `LEFT_BRACKET` |
| `#` | `HASH` |
| `$` | `LS(NUMBER_4)` |
| `%` | `LS(NUMBER_5)` |
| `^` | `EQUAL`（^~ キー・無シフト） |
| `&` | `LS(NUMBER_7)` |
| `*` | `LS(SINGLE_QUOTE)` |
| `(` | `LS(NUMBER_8)` |
| `)` | `LS(NUMBER_9)` |
| `_` | `LS(MINUS)` |
| `+` | `LS(EQUAL)` |
| `=` | `LS(MINUS)` |
| `` ` `` | `LS(LEFT_BRACKET)` |
| `"` | `LS(NUMBER_2)` |
| `'` | `LS(NUMBER_7)` |
| `~` | `LS(EQUAL)` |
| `{` | `LS(LEFT_BRACKET)` |
| `}` | `LS(RIGHT_BRACKET)` |
| `[` | `RIGHT_BRACKET` |
| `]` | `BACKSLASH` |
| `:` | `LS(SEMICOLON)` |
| `;` | `SEMICOLON` |
| `\` | `NON_US_BACKSLASH`（106 `\` 物理と同系） |
| `\|` | `LS(INT3)` |

## `win_symbol`（mac 同一位置 → win Output）

| 位置（mac の記号意図） | mac (`mac_symbol`) | win (`win_symbol`) |
|------------------------|--------------------|--------------------|
| `?` `!` `&` `\|` `\` | `QUESTION` … `BACKSLASH` | 同左のうち `&`→`LS(N7)`, `\|`→`LS(INT3)`, `\`→`NON_US_BACKSLASH` |
| `/` `=` `*` `+` `%` | `SLASH` … `PERCENT` | `SLASH`, `LS(MINUS)`, `LS(SQT)`, `LS(EQUAL)`, `LS(N5)` |
| `` ` `` `"` `'` `~` `^` `_` | `GRAVE` … `UNDER` | `` ` ``→`LS(LBKT)`, `"`→`LS(N2)`, `'`→`LS(N7)`, `~`→`LS(EQUAL)`, `^`→`EQUAL`, `_`→`LS(MINUS)` |
| `@` … `$` | `AT_SIGN` … `DOLLAR` | `@`→`LBKT`, `{[`→`LS(LBKT)`/`RBKT`, `()`→`LS(N8)`/`LS(N9)`, `:;`→`LS(SEMI)`/`SEMI`, `[]`→`BSLH`/`LS(RBKT)`, `$`→`LS(N4)` |

（`SQT` = `SINGLE_QUOTE`, `LBKT` = `LEFT_BRACKET`, `RBKT` = `RIGHT_BRACKET`, `SEMI` = `SEMICOLON`, `N5` = `NUMBER_5` など）

## `win_num` 右上段（写真どおり）

mac: `/` `=` `*` `+` `%` → win: `QUESTION`（`?`）, `LS(MINUS)`（`=`）, `LS(SINGLE_QUOTE)`（`*`）, `LS(EQUAL)`（`+`）, `LS(NUMBER_5)`（`%`）。

右下 `$` → `LS(NUMBER_4)`、`|` → `LS(INT3)`。

## 実機確認

表どおりでも **IME 状態**で結果が変わることがある。ずれるキーは **レイヤー名・キー位置・期待文字・実際の文字** をメモして調整する。

参考: 同梱 `Cygnusマニュアル-20260609.pdf`「JIS-US 文字＆変換キー対応表」、`config/Cygnus.keymap` コメント。
