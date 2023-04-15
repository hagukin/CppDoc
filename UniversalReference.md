# 보편 참조(Universal Reference, AKA Forwarding Reference)  
생각보다 상당히 중요한 개념이므로 잘 이해하자.  

[참고글 - 권장](http://egloos.zum.com/sweeper/v/3149089)  
https://blog.insane.pe.kr/1449  

## 개념 정리
다 정리하기엔 양이 많고, 핵심 부분들만 간추렸다. 추가적인 정보는 원문 참조  

1) &&라고 다 rvalue reference를 의미하는 게 아니다.  
2) 어떤 변수나 인자가 type deduction(추론)이 필요하며, 정확히 "T&&"로 선언되면, 해당 변수나 인자는 universal reference이다.  
3) Type deduction이 필요한 경우는 auto 변수를 사용하는 경우나, 혹은 템플릿을 사용하는 경우가 있다.  
```c++
Widget&& var1 = someWidget;     // rvalue ref 
auto&& var2 = var1;             // rvalue ref or lvalue ref (universal ref)
 
template <typename T>
void f(std::vector<T>&& param); // rvalue ref
 
template <typename T>
void f(T&& param);              // rvalue ref or lvalue ref (universal ref)
```
4) 예시:  
이해를 위해 l,r value에 대한 이해가 필요하다.  
```c++
Widget&& var1 = someWidget;
auto&& var2 = var1;
```  
위 코드에서 var1은 lvalue이다. 왜? 타입을 선언하기를 rvalue로 선언했지만, someWidget을 건내주어 주소를 확실히 알 수 있기 때문이다.  
auto&&는 universal reference인데, var1이 lvalue이므로, var2도 lvalue이다.  

```c++
template <typename T>
void f(T&& param);
 
// 주소를 취할 수 없는 literal 10은 rvalue
// 따라서, param은 rvalue reference (int&&)
f(10);
 
// 주소를 취할 수 있는 x는 lvalue
// 따라서, param은 lvalue reference (int&)
int x = 10;
f(x);
```  
5) "&&"이 universal reference를 의미하는 경우는 타입 추론이 필요한 경우만이라는 것을 잊지 말아야 한다.
이 말을 뒤집으면, 타입 추론이 아닌 명시가 되어 있는 경우에는 "&&"는 늘 rvalue reference를 의미한다는 소리다.  
```c++
template <typename T1>
class Gadget
{
    ...
    template <typename T2>
    Gadget(T2&& rhs);        // T2에 대한 타입 추론이 필요. && ≡ universal reference
};
 
void f(Widget&& param);      // 명시적인 Widget 타입. && ≡ rvalue reference
```  
6) 흥미로운 경우:  
```c++
template <typename T>
void f(std::vector<T>&& param); // rvalue ref
```
이 경우 타입이 vector<T>로 분명하기 때문에 rvalue이다!  
7) 실제 문제 사례: IOCP PacketHandler 18:00가량부터 흥미로운 사례가 나온다.  
해결법을 눈여겨 볼 필요가 있는데, [std::remove_reference](https://2pound2pound.tistory.com/254)를 사용해 타입만을 추출하는 방식으로 Type&*꼴에서 발생하는 문법오류를 잡아주었다.  
