無線キーボード Cygnus の ZMK ユーザー設定（**Windows 標準層 = JIS 106 配列**）。

- ベースリポジトリ: [Cygnus-S-Lkeymouse](https://github.com/Yoshihiro-Kameoka/Cygnus-S-Lkeymouse)（`win_base` は US 配列）
- 本リポジトリ: **マニュアル「JIS-US 文字＆変換キー対応表」** に沿い `win_num` / `win_symbol` を定義。`mac_num` / `mac_symbol` は本体 US 配列のまま（[詳細](docs/jis-us-layers.md)）
- `win_base` は JIS 向け（`@` `\` など）。**L 右は Mac 同様 `MINUS`（`-`）**（`SEMICOLON` ではない）
- 使い方は Cygnus 付属マニュアルを参照
- **ZMK Studio**: `INT3` / `LS(INT3)` / `LS(MINUS)` 等は表示が分かりにくいことがある。**赤丸のまま保存しない**。不調時は Actions の UF2 を再フラッシュ
