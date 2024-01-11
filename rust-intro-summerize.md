---
marp: true
theme: default
class: invert
---
<style>
@import url("https://fonts.googleapis.com/css?family=Noto+Sans+JP");
section {
  font-family: "Noto Sans JP";
  font-size: 26px;
  background:linear-gradient(60deg, #2c4560, #23453b);
  justify-content: start;
}
</style>

# Rust 入門 まとめ

---
# [Rust](https://www.rust-lang.org/ja) とは

**速い**
- C++と同じくらい速いらしい。ガベージコレクションがない

**安全**
- 所有権の概念のおかげで（ガベージコレクションがなくても）メモリ安全、スレッド安全

**生産性が高い（らしい）**
**マルチパラダイム**
- 手続き的にも関数型的にも書ける

**そして[オープンソース](https://github.com/rust-lang/rust)**

