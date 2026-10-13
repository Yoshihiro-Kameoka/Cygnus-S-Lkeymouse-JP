無線キーボード Cygnus の ZMK ユーザー設定（**Windows 標準層 = JIS 106 配列**）。

- ベースリポジトリ: [Cygnus-S-Lkeymouse](https://github.com/Yoshihiro-Kameoka/Cygnus-S-Lkeymouse)（`win_base` は US 配列）
- 本リポジトリ: `win_base` は JIS 106 物理キー、`win_symbol` は本体 `symbol`（US キーコード）を [zmk-layout-shift の US→JIS 対応](https://github.com/kot149/zmk-layout-shift/blob/v2/dts/layout_shift_maps.dtsi) 相当で変換。`mac_*` は US 配列のまま
- 使い方は Cygnus 付属マニュアルを参照
- **ZMK Studio**: `win_symbol` の `¥` / `|` / `_` は `INT3` / `LS(INT3)` / `LS(INT1)` を使用（`0x89` 等の直書きは Studio が未対応で赤表示になり、保存するとキーが空になることがある）。不調時は GitHub Actions の UF2 を再フラッシュし、Studio で上書き保存しない
