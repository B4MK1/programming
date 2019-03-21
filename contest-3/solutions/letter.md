# Үсэг

Энэхүү бодлогын зорилго нь тэмдэгт мөр мөн тэмдэгт мөрийн нэг үсгийн ард орших [ASCII](http://www.asciitable.com/) кодын талаар ойлголт өгөх байсан.

ASCII кодыг илүү ойлгоцгооё. 
Доорх код ба гаралтаас үзвэл нэг үсэг бүрийн ард бүхэл тоо байдгийг харж болно.

### Код 1

```
char a = 'a';
char b = 'b';
char c = 'c';
char z = 'z';
char A = 'A';
char B = 'B';
char C = 'C';
char Z = 'Z';

cout << int(a) << endl;
cout << int(b) << endl;
cout << int(c) << endl;
cout << int(z) << endl;
cout << "-------" << endl;
cout << int(A) << endl;
cout << int(B) << endl;
cout << int(C) << endl;
cout << int(Z) << endl;
```

Дээрх кодын гаралт

```
97
98
99
122
-------
65
66
67
90
```

Хамгийн олон орсон үсгийг олохын тулд том үсгүүдийг жижиг болгож хувиргах шаардлага гарсан.

## Том үсгийг жижиг болгох

Код 1-т гарсанаар 'a' үсгийн код нь 97 харин 'A' үсгийн код нь 65 гэдгийг харж болно. Тэгвэл том үсэг байвал код дээр нь 32-ыг нэмэх юм бол жижиг үсэг нь гараад ирч байна.

## Бодлогоо задлах 

Эхний алхам том үсгийг жижиг болгох.

2 дугаар алхам үсэг бүрийг хэд орсныг тоолох.

3 дугаар алхам хамгийн олон орсон үсгийг хэвлэх.


## Код 2

```
#include <iostream>

using namespace std;

int main() {
    int i, b[26] = {0}, x = 0, ma = 0, _index = 0;
    string s;

    cin >> s;
    for (i=0;i<s.length();i++)
        if ('A' <= s[i] && s[i] <='Z') // Том үсэг эсэхийг шалгах
            s[i] = char(s[i] + 32); // Жижиг үсэг болгох

    // Хамгийн олон орсон үсгийг олох
    for (i=0;i<s.length();i++) {
        x = s[i] - 'a';
        b[x] ++;
        if (b[x] > ma) {
            ma = b[x];
            _index = x;
        }
    }

	cout<<char(_index + 'a') <<endl;

    return 0;
}
```

## Author: LBayarkhuu