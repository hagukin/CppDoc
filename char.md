char 배열은 한번의 cout으로 문자열 형태로 출력이 가능하다.
```
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
