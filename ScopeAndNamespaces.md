앞에 아무 문자열도 붙지 않은 스코프 식별 연산자 :: 는 전역 스코프를 의미한다.  
```c++
int x = 10000;
int main()
{
    int x = 10;
    cout << x << " " << ::x << endl;
    // 출력: 10 10000
    return 0;
}
```