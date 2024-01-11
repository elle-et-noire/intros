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

# Coq でソートを実装 まとめ

---

# 実装したソート

https://arxiv.org/abs/2110.01111

[Wikipadia](https://en.wikipedia.org/wiki/Sorting_algorithm)には "I Can't Believe It Can Sort" として載っている。

```python
def sort(A):
  for i in range(len(A)):
    for j in range(len(A)):
      if A[i] < A[j]:
        A[i], A[j] = A[j], A[i]

A = [1,5,6,2,7,3,4]
sort(A)
print(A) # [1,2,3,4,5,6,7]
```

---

# 完成物

[ソースコード](https://github.com/elle-et-noire/coq-wsl/blob/main/sort/simplest01.v)

[jsCoq](https://coq.vercel.app/scratchpad.html)などで実行すると無事ソートであることが証明できる。
