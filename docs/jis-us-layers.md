# JIS-US レイヤー（Cygnus マニュアル準拠）

ZMK / Studio は **US 配列の Output（送るキーコード）** 前提。OS を **日本語 JIS 106** にしているとき、同じ Output でも画面に出る文字は **マニュアルの「JIS Keyboard」列** になる。

JP リポジトリでは次を分離する。

| レイヤー | Win (BT0) | Mac (BT1/2) |
|----------|-----------|-------------|
| 数字・記号 | `win_num` / `win_symbol` | `mac_num` / `mac_symbol` |
| 入口 | `win_base` の LANGUAGE_2 / ENTER 長押し | `mac_base` 同様 |

## 変換の考え方

1. **mac_* 側** … 本体 Cygnus と同じ US Output（Studio の表示 ≒ US キー）
2. **win_* 側** … 同じキー位置で **同じ記号を JIS OS に出したい** とき、マニュアル **JIS-US 文字＆変換キー対応表** の Output 列に差し替える

代表例（Shift 行）:

| 出したい記号 | win 側の Output |
|--------------|-----------------|
| `_` | `LS(MINUS)` |
| `+` | `LS(EQUAL)` |
| `:` | `LS(SEMICOLON)` |
| `*` | `LS(SINGLE_QUOTE)` |
| `"` | `LS(NUMBER_2)` |
| `&` | `LS(NUMBER_6)` |
| `(` | `LS(NUMBER_8)` |
| `)` | `LS(NUMBER_9)` |
| `$` | `LS(NUMBER_4)` |
| `\|` | `LS(INT3)` |
| `¥` | `INT3` |

記号行: `^`→`EQUAL`, `=`→`MINUS`, `[`→`RIGHT_BRACKET`, `]`→`BACKSLASH`, `:`→`LS(SEMICOLON)`, `;`→`SEMICOLON` など。

## NUM レイヤー（写真配置）

右側上段は mac で `/ = * + %`（US Output）。win では JIS 向けに:

- `?` … `QUESTION`（`?` / `/` キー）
- `+` … `LS(EQUAL)`（表の Shift+`=`）
- `*` … `LS(SINGLE_QUOTE)`（表の Shift+`'`。写真の `(S+8*)` は US 側の対応関係の注記）
- `%` … `LS(NUMBER_5)`
- 右下 `$` … `LS(NUMBER_4)`、`|` … `LS(INT3)`

## 参考

- 同梱マニュアル「JIS-US 文字＆変換キー対応表」
- `config/Cygnus.keymap` 先頭コメント
