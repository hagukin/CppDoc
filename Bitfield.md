* (C/C++) Bitfield - 굳이 모든 비트를 다 쓸 필요가 없을 때 Struct 내에서 어떤 자료형이 딱 필요한 비트만큼만 차지하게 만들어 메모리를 줄이는 방법  
https://stackoverflow.com/questions/3186008/in-c-what-does-a-colon-mean-inside-a-declaration  
https://www.it-note.kr/312  

구조체 내 정수형 멤버들만 있을 경우 사용 가능하며, 구조체는 그 정수형 멤버들중 가장 크기가 큰 멤버의 크기만큼 비트를 차지한다.  
