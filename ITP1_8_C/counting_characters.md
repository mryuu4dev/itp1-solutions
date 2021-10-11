## 問題文要旨
- 英文のアルファベットの数をカウントし出力せよ
- 大文字, 小文字を区別しない
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	char ch;
	int ans[26] = {};
	int i;

	while (cin >> ch) {
		if (65 <= ch && ch <= 90) {
			ch += 32; // 小文字に変換
		}
		ans[ch - 'a'] ++;
	}

	for (i = 0; i < 26; i++) {
		cout << char(i + 'a') << " : " << ans[i] << endl;
	}
}
```
## 学んだこと
### EOFまでの読み込み(C++)
- Cの場合
    ```c
    char ch;

    while ( scanf("%c", &ch) != EOF ){
        /* 処理 */ 

    }
    ```
- C++の場合
    ```cpp
    char ch;

    while ( cin >> ch ){
        // 処理

    }
    ```
### EOFをwindowsで発生させるには
- Ctl+Zとenterを押す. enterを忘れないこと

## 参考
- [while (scanf("%d %s", &key, name) != EOF)の挙動がおかしい](https://teratail.com/questions/159303)