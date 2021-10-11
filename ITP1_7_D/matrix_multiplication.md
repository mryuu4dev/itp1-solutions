## 問題文要旨
- 行列Aと行列Bの積を出力せよ
- 入力: `A(n × m)`, `B(m × l)`
- 出力: `C(n × l)`
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, m, l;
	int A[100][100], B[100][100];
	long long int c_elem = 0;
	int i, j, k;

	cin >> n >> m >> l;

	// 行列A 入力
	for (i = 0; i < n; i++) {
		for (j = 0; j < m; j++) {
			cin >> A[i][j];
		}
	}

	// 行列B 入力
	for (i = 0; i < m; i++) {
		for (j = 0; j < l; j++) {
			cin >> B[i][j];
		}
	}

	for (i = 0; i < n; i++) {
		for (j = 0; j < l; j++) {
			for (k = 0; k < m; k++) {
				c_elem += A[i][k] * B[k][j];
			}
			cout << c_elem << (j != l - 1 ? " ": "");
			c_elem = 0;
		}
		cout << endl;
	}
}
```
## 注意点
- 下記の式より3重ループが必要


[![Image from Gyazo](https://i.gyazo.com/b75f5a1a48e981d1593326eb1ed6e5d5.png)](https://gyazo.com/b75f5a1a48e981d1593326eb1ed6e5d5)
- Aの要素の最大値, Bの要素の最大値ともに10^4で, mの最大値が10^2より, Cの値が最大10^10になる可能性がある
    - したがって, `long long int`型を用いるべきである