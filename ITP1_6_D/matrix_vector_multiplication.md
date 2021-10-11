## 問題文要旨
- 行列A(n × m)とベクトルb(m × 1)の積を求めよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    /* 入力ここから */
    int n, m;
    int A[100][100] = {}, b[100] = {};
    /* 入力ここまで */
    int ci = 0;
    int i, j;

    cin >> n >> m;

    /* 行列Aの入力 */
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            cin >> A[i][j];
        }
    }

    /* ベクトルbの入力 */
    for (i = 0; i < m; i++) {
        cin >> b[i];
    }

    /* A × b の計算 */
    for (i = 0; i < n; i++) {
        for (j = 0; j < m; j++) {
            ci += A[i][j] * b[j];
        }
        cout << ci << endl;
        ci = 0;
    }
}
```
## 学んだこと
### 行列とベクトルの積
- 下記の式より2重ループが必要


[![Image from Gyazo](https://i.gyazo.com/79166f782d3b7845e715d83eb00e7e99.png)](https://gyazo.com/79166f782d3b7845e715d83eb00e7e99)