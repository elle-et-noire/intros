---
marp: true
theme: default
class: invert
---
<style>
section {
  background:linear-gradient(to right, #2c4560, #23453b);
  justify-content: start;
}
</style>

# Julia 入門 まとめ

---
# Julia とは

**速い**
- LLVM を利用してネイティブコードを生成する（らしい）

**簡単に書ける**
- 動的型付けのおかげで気軽に書ける。対話環境も充実。

**いろいろな構成に対応**
- 多重ディスパッチでOOP（構造体に関数が作用する書き方）や関数型っぽく書ける

**そして[オープンソース](https://github.com/JuliaLang/julia)**

<!-- 参考：[Julia in a Nutshell](https://julialang.org/), [なぜ僕らはJuliaを作ったか](https://www.geidai.ac.jp/~marui/julialang/why_we_created_julia/index.html) -->
<div style="text-align: right"> 参考 <a href="https://julialang.org/">Julia in a Nutshell</a>, <a href="https://www.geidai.ac.jp/~marui/julialang/why_we_created_julia/index.html">なぜ僕らはJuliaを作ったか</a> </div>

