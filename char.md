char 배열은 한번의 cout으로 문자열 형태로 출력이 가능하다.
```c++
int main()
{
    char test[15];
    for (char i=0;i<15;++i)
    {
        test[i] = 'a'+i;
    }
    cout << test;
    return 0;
}
// 출력: abcdefghijklmno
```
  
char 배열은 문자열 형태로 한번에 초기화가 가능하다.
```c++
char test[100] = "Hello World";
// 빈공간은 null로 채워짐
```

TCHAR, WCHAR - 유니코드와 MBCS  
https://redcoder.tistory.com/137  
