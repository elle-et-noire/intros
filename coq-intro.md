---
marp: true
# backgroundColor: orange
theme: gaia
class: invert
---
<style>
section {
  background:linear-gradient(60deg, #4c8590, #734b85);
}
</style>

# Coq 入門

---
# 定理証明支援系とは

- 証明が正しいことを検証してくれる装置。
- 公理から定理の証明を構築する手順を、型システムで模倣する。
- （証明は人間が作る）
- 検証だけでなく、証明の構築も支援してくれる。

定理証明支援系の１つとして **Coq** がある。

---
# インストール
Coq 8.8.0 まではインストーラが用意されている。最新は 8.16.0

- **新しさより簡単さ重視する人**：[レポジトリ](https://github.com/coq/coq/releases/tag/V8.8.0)からインストーラを入手

- **最新版を入れたい人**：[Coq/SSReflect/MathCompの設定](https://staff.aist.go.jp/reynald.affeldt/ssrcoq/install.html#org35ada1b)に従う
  - `sudo apt get install`でなく`sudo apt install`
  - WSLでは「新しいライブラリの設定が要るかも」の箇所で`sudo apt install -y libgmp-dev`が必要だった([参考](https://www.aise.ics.saitama-u.ac.jp/~gotoh/Coq-SSReflect-MathCompOnUbuntu2004.html))

---
# エディタ

- **VScode+VSCoq** がおすすめ。VScode上で拡張機能(`Ctrl+Shift+X`)から「vscoq」と検索すれば出てくる。
  - Windowsの人はWSL上で動かせるように **Remote - WSL** も入れよう（「wsl」で検索）。

- **CoqIDE** もインストーラから入れた場合は利用できる（がVSCoqの方が便利）

- [**Emacs** 上で **Proof General** を動かす手段](https://www.aise.ics.saitama-u.ac.jp/~gotoh/Coq-SSReflect-MathCompOnUbuntu2004.html)もあるらしい。

