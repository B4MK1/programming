# Chessboard
_**N x M**_ хэмжээтэй шатрын хөлгийг хэвлэ. Шатрын хөлгийн хар нүдийг "#"-аар, цагаан нүдийг "`_`"-аар илэрхийлэх ба баруун доод булан дахь нүд ямагт хар өнгөтэй байх ёстой.

## Бодолт
Эхлээд дараах 2 санамжийг саная.

#### Санамж 1
Шатрын хөлгийн аль ч хоёр хөрш нүднүүд эсрэг өнгөтэй байна.
#### Санамж 2
Бидний хэвлэх шатрын хөлгийн баруун доод булан ямагт хар өнгөтэй байх ёстой.

Энэ хоёр санамжыг ашиглан _**i**_ дэх мөрний _**j**_ дэх нүд ямар өнгөтэй болохыг хялбархан тодорхойлж чадах юм. Доорх зурагт үзүүлсэний дагуу баруун доод булангийн хар өнгөтэй нүднээс _**i**_ дэх мөрний _**j**_ дэх нүдийг улаан сумын дагуух замаар холбоё.

<img src="https://i.imgur.com/ffaOFjv.png" alt="chessboard" width="400"/>

Улаан сумын дагуу нийт _**(N - i) + (M - j) + 1**_ ширхэг нүд байна. Энд _**Санамж 1**_-ийг санавал энэ хөрш нүднүүд ч мөн адил эсрэг өнгөтэй байх ёстой. Мөн _**Санамж 2**_-ын дагуу баруун доод булангийн нүд ямагт хар өнгөтэй байх ёстой тул _**(N - i) + (M - j) + 1**_-ийн утга тэгш, сондгойгоос хамааран бид _**i**_ дэх мөрний _**j**_ дэх нүд ямар өнгөтэй болохыг тодорхойлж чадна.
* Хэрвээ _**(N - i) + (M - j) + 1**_-ийн утга **тэгш** бол  _**i**_ дэх мөрний _**j**_ дэх нүд цагаан өнгөтэй байна.
* Хэрвээ _**(N - i) + (M - j) + 1**_-ийн утга **сондгой** бол  _**i**_ дэх мөрний _**j**_ дэх нүд хар өнгөтэй байна.

### Code
```
#include <iostream>
using namespace std;

int main() {
    int N, M;
    cin >> N >> M;

    for (int i = 0; i < N; i++) {
        for (int j = 0; j < M; j++) {
            if ((N - i + M - j + 1) % 2 == 1) {
                cout << "#";
            } else {
                cout << "_";
            }
        }
        cout << endl;
    }
    return 0;
}
```

### Geek code - 9 мөр
Энэ код хэдий 9 мөр ч гэсэн дээрх бичсэн кодтой яг адил ажиллана.

```
#include <iostream>
using namespace std;
int main() {
    int N, M;
    cin >> N >> M;
    for (int i = 0; i < N; i++, cout << endl)
        for (int j = 0; j < M; j++)
            (N - i + M - j) % 2 == 0 ? cout << "#" : cout << "_";
}
```