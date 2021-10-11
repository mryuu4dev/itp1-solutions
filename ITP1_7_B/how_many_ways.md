## 問題文要旨
- 1 ~ nの中から3つの数を選び(重複なし), 合計がxとなる組み合わせの個数を出力せよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, x;
    int i, j, k;
    int cnt = 0;

    while (1) {
        cin >> n >> x;
        if (n == 0 && x == 0) {
            break;
        }
        // ループの開始, 終了条件について気を付けること
        for (i = 1; i <= n - 2; i++) {
            for (j = i + 1; j <= n - 1; j++) {
                for (k = j + 1; k <= n; k++) {
                    if (i + j + k == x) {
                        cnt++;
                    }
                }
            }
        }
        cout << cnt << endl;
        cnt = 0;
    }
}
```