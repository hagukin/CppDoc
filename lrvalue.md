* Universal reference, Forwarding reference  
https://quuxplusone.github.io/blog/2022/02/02/look-what-they-need/  
-> Reference.md 참고  

* l-r value  
http://sweeper.egloos.com/2978540  

* std::move와 move semantics  
https://kukuta.tistory.com/425  
https://kukuta.tistory.com/426  
흔히 std::move에 대해 오해하는 부분은 std::move 함수를 호출하기만 하면 C++에서 내부적으로 원본 객체의 자원을 빼앗아 대상 객체로 이동 시켜주는 것이라 오해하는데, 실제 move에 관련된 연산은 move 생성자나 move 대입연산자에서 구현 해주어야 한다. 실제 자원을 옮기는 작업은 클래스를 설계하는 작성자가 직접 구현해주어야 한다.  
