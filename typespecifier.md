* 함수 파라미터 앞에 class 키워드를 붙여주는 이유는 타입과 변수명을 확실히 구문짓기 위함이다
```c++
// https://en.cppreference.com/w/cpp/language/elaborated_type_specifier
class T {
public:
    class U;
private:
    int U;
};

int main()
{
    int T;
    T t; // error: the local variable T is found
    class T t; // OK: finds ::T, the local variable T is ignored
    T::U* u; // error: lookup of T::U finds the private data member
    class T::U* u; // OK: the data member is ignored
}
```
