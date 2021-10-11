## 問題文要旨
- 文字列の小文字と大文字を入れ替え, 出力せよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	string str;
	int i;

    // 空白を無視する
	getline(cin, str);

	for (i = 0; i < str.length(); i++) {
		if (97 <= str[i] && str[i] <= 122) {
			str[i] -= 32; // 大文字に変換
		}
		else if (65 <= str[i] && str[i] <= 90) {
			str[i] += 32; // 小文字に変換
		}
	}

	cout << str << endl;
}
```
## 学んだこと
### 符号化文字集合
- 「文字」と「文字に割り当てた番号」の対応表
- JIS X 0208, Unicode など
### 文字符号化方式
- 「文字に割り当てた番号」と「実際にコンピュータが扱う数字」の対応表
- Shift-JIS, EUC-JP, UTF-8
### アスキーコード
- 「文字」と「実際にコンピュータが扱う数字」が対応する
- つまり「文字に割り当てた番号」,「実際にコンピュータが扱う数字」が同じ
- 基本プログラムで扱うときはこっち? (この問題でもアスキーコードを使った)

## 参考
- [符号化文字集合](https://wa3.i-3-i.info/word15291.html)
- [主な文字集合と符号化方式](https://www.tohoho-web.com/ex/charset.html#charset_and_encoding)
    - 文字集合と符号化方式の対応表