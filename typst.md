---
marp: true
theme: default
class: invert
---
<style>
section {
  background:linear-gradient(to right, #2c4560, #23453b);
}
h1{
    position: absolute;
    left: 50px; top: 50px;
}
</style>

# Typst 入門

---

## LaTeX のコンパイル、遅くない...？



## LaTeX のコマンド、長くない...？

---



# なぜ Typst なのか


他の組版ソフトウェア（LaTeX、SATySFi など）に比べて

- コンパイルが速い
  - 出来上がりを見ながら編集できる

- 環境構築が楽

- 書き方がシンプル

- Rust 製

- できて間もない（2023年公開）
  - 今後の伸びしろに期待できる

---

# 環境

- 手元の環境構築：https://github.com/typst/typst#installation
  - Linux: View [Typst on Repology][repology]
  - macOS: `brew install typst`
  - Windows: `winget install --id Typst.Typst`

- Rustの環境が整っていれば cargo から入れるのが簡単。
`cargo install --git https://github.com/typst/typst typst-cli`

- オンラインエディタ [Typst: Compose papers faster](https://typst.app/) もある。
  - アカウント登録が必要。

---

# コンパイル

- `typst compile ファイル名`でコンパイル
  - 出力ファイル名も指定できる `typst compile 入力名 出力名`

- `typst watch ファイル名`でリアルタイム監視

- [Typst LSP - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=nvarner.typst-lsp) を入れておいてVSCodeで保存すれば勝手にコンパイルしてくれる

---

# 主な記法

Markdown を思わせるシンプルな記法が用意されている。

- **太字**は `*`、斜体は `_`、タイプライターは `` ` `` で囲む

- 見出しは `=` を何個か並べる

- コメントは `\\` か `/* ... */`

- 箇条書きは `-`、番号リストは `+`

詳しくは [さらばTex。Typstの文法全集 〜1. マークアップ編〜 (zenn.dev)](https://zenn.dev/yuhi_ut/articles/how2write-typst1#%E6%96%87%E5%AD%97%E4%BF%AE%E9%A3%BE%E4%B8%80%E8%A6%A7) を参照。

---

# 数式

こちらも $\LaTeX$ よりシンプルな書き方ができる。

$\LaTeX$ で
```LaTeX
$$\dfrac{\partial\mathcal{L}}{\partial q_i}-\dfrac{d}{dt}\dfrac{\partial\mathcal{L}}{\partial\dot{q}_i}=0$$
```
と書かなければいけないところが Typst では
```Typst
$ (diff cal(L)) / (diff q_i) - d / (d t) (diff cal(L)) / (diff dot(q_i)) = 0 $
```
で済む！

---

# フォント

- `#set text(font: "Hiragino Kaku Gothic Pro")`のようにフォントを指定できる。


- 使えるフォントは`typst fonts`で確認できる。

---

# Typst のここがダメ！

- 数式の細かい調整ができない
  - 一文字だけローマン体にすることができない（自分調べ）
  - スペースを調整できない（自分調べ）

- デフォルトの組版が汚い
  - セクション名とナンバリングの数字が近すぎる


## 今後の進展に期待！

---


# 参考

- [もうTeXは時代遅れ！？ はじめてのTypstマニュアル (zenn.dev)](https://zenn.dev/yuhi_ut/articles/how2start-typst)

- [さらばTex。Typstの文法全集 〜1. マークアップ編〜 (zenn.dev)](https://zenn.dev/yuhi_ut/articles/how2write-typst1)

- [Typst Documentation](https://typst.app/docs)