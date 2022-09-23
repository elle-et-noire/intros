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

- [**jsCoq**](https://coq.vercel.app/scratchpad.html)：ブラウザ上で動くCoq。


---
# まずは簡単な例。

```coq
Section ModusPonens.
Variables P Q : Prop.
Theorem MP : P -> (P -> Q) -> Q.
Proof.
  intros Pis PimpliesQ.
  apply PimpliesQ.
  apply Pis.
Qed.
```

VSCoq, jsCoq上では`Alt+↓`で１文ずつ証明が読み込まれる。

---
ここで `Print MP.` を実行すると
```coq
MP = 
fun (Pis : P) (PimpliesQ : P -> Q) =>
PimpliesQ Pis
     : P -> (P -> Q) -> Q

Arguments MP _ _%function_scope
```
のように表示される。

つまり`MP`とは、引数として`Pis`(値)と`PimpliesQ`(関数)を受け取って`PimpliesQ Pis`を返す関数。

---
Coqの(正確には**Gallina**の)書式は`変数名 : 型`。

`MP`の型`P -> (P -> Q) -> Q`は、`P`型の値と`P->Q`型の値(関数)を受け取って`Q`型の値を返す関数、を意味する。

これを、「Pという言明の証明とP->Qという言明の証明を受け取ってQという言明の証明を作る」ことと同一視する。
　　　　　　　　　　　　　　　　　　　→ **Curry-Howard同型対応**

---
# Curry-Howard同型対応における解釈

|論理演算|解釈|
|:-:|:-:|
|$A\land B$|$A$の証明と$B$の証明のペアの集合（直積集合）|
|$A\lor B$|$A$の証明の集合と$B$の証明の集合の和集合|
|$A\to B$|$A$の証明からの$B$の証明の構成方法の集合|
|$\forall x\colon A, B(x)$|$A$の証明$x$からの$B(x)$の構成方法の集合（依存型）|
|$\exists x \colon A, B(x)$|$A$の証明$x$からの$B(x)$の構成方法の集合（依存型）|
---
# リンク集
- [Coq クィックリファレンス](https://magicant.github.io/programmingmemo/coq/)
  　事例集をみればとりあえず証明が書ける。

- [TopProver](https://top-prover.top/)
  　競プロのCoq版。最近はコンテストは開かれていないが過去問で証明の練習ができる。

- [Coq/SSReflect/MathComp Tutorial](https://staff.aist.go.jp/reynald.affeldt/ssrcoq/)
　スライドとかExample がいろいろ載ってる。

- [ソフトウェアの基礎](http://proofcafe.org/sf/toc.html)
　網羅的に勉強できそう。

---
# 参考文献

- [萩原学/アフェルト・レナルド『Coq/SSReflect/MathComp による定理証明』(森北出版，2018)](https://www.morikita.co.jp/books/mid/006241)　必携。
- [定理証明支援系 Coq による形式検証（PDF）](https://staff.aist.go.jp/reynald.affeldt/ssrcoq/coq-kyoto2015.pdf)