## 問題文要旨
- `n`個の整数`a`の最小値、最大値、合計値を出力せよ
- 制約
    - `0 < n ≤ 10000`
    - `-1000000 ≤ a ≤ 1000000`
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, a;
	int max = -1000000, min = 1000000;
	long long int sum = 0;
	int i;

	cin >> n;

	for (i = 0; i < n; i++) {
		cin >> a;

		if (max < a) {
			max = a;
		}

		if (min > a) {
			min = a;
		}

		sum += a;
	}

	cout << min << " " << max << " " << sum << endl;
}
```
## 学んだこと
### 型の表現範囲(C++)
- [変数の表現範囲](https://judge.u-aizu.ac.jp/onlinejudge/commentary.jsp?id=ITP1_4_D&pattern=pre&type=language)
    - つまり, 1 * 10^-9 ~ 1 * 10^9 くらいまでならintで計算できる
    - あれ, `int`, `long`の表現できる範囲って同じなんだ..
### この問題の考え方
- aの最大値, 1 * 10^6が, nの最大値, 1 * 10^4 個あるとすると, 1 * 10^10が合計値の最大となる