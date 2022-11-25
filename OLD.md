모던C++ 관련 참조할만한 레퍼런스  
https://jungwoong.tistory.com/category/c%2B%2B/modern%20c%2B%2B  

* const vs constexpr  
https://haedallog.tistory.com/81  

* switch 문 내에서 변수를 선언할 경우 꼭 {}로 블록을 나눠놓아야 한다.  
https://blankspace-dev.tistory.com/386  

* char '1' '2' 등을 int로 변환하는 법  
char c = '4';  
int ci = c - '0'; // 아스키표 상에서 4와 0은 4만큼 인덱스가 차이나므로 구해진다.  

* std::chrono, std::mutex, std::thread, std::atomic
    * lock_guard<mutex>(m)
    * thread.join()
    * atomic<bool> _locked.compare_exchange_strong(expected, desired);
    * this_thread::sleep_for(std::chrono::milliseconds(100));
    * this_thread::sleep_for(100ms);
    * this_thread::yield(); (=sleep_for(0);)
    
* std::transform
    범위 기반 함수 처리  
    * https://artist-developer.tistory.com/28  

* Effective c++ 요약본 (~5장까지)
    * https://husk321.tistory.com/  

* 스마트포인터 정리  
    * http://www.tcpschool.com/cpp/cpp_template_smartPointer  
    * https://gamdekong.tistory.com/87  
    * http://egloos.zum.com/sweeper/v/3059940   - Weak pointer로 shared_ptr에서 발생할 수 있는 circular reference 문제를 해결
* (C/C++) Bitfield - 굳이 모든 비트를 다 쓸 필요가 없을 때 Struct 내에서 어떤 자료형이 딱 필요한 비트만큼만 차지하게 만들어 메모리를 줄이는 방법  
    * https://stackoverflow.com/questions/3186008/in-c-what-does-a-colon-mean-inside-a-declaration  

* std::atomic
    * http://egloos.zum.com/sweeper/v/3059861  
    
* thread_local (TLS)
    * https://stormpy.tistory.com/m/168  
* 함수 포인터보다 std::function의 사용이 권장된다
    * https://yhwanp.github.io/2019/09/15/std-function-and-std-bind/  
    
* 함수 내에서 전역(static)변수를 선언할 때 이 변수의 lifetime은 얼마인가?  
    * https://stackoverflow.com/questions/246564/what-is-the-lifetime-of-a-static-variable-in-a-c-function  
    
* extern을 이용한 다른 파일에서 선언된 전역변수 사용하는 법
    * 간략한 설명: https://hazarddev.tistory.com/56
    * 올바른 사용법(extern 남발을 자제하려면): https://velog.io/@luckyhan/C-extern-%EB%B3%80%EC%88%98-%EC%A0%95%EB%A6%AC  
    
* typeid  
   https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kyed203&logNo=220164579551  
   
* virtual 소멸자의 필요성  
    http://hyacinth.byus.net/moniwiki/wiki.php/C%2B%2B/%EC%86%8C%EB%A9%B8%EC%9E%90%EC%97%90%20virtual%EC%9D%84%20%EC%93%B0%EB%8A%94%20%EC%9D%B4%EC%9C%A0  
    
* C++ 동적할당된 메모리는 스코프 밖이라도 자동으로 해제되지 않는다  
    https://wiserloner.tistory.com/286   
    
* 상속이 런타임에서의 성능 저하를 유도하는가?  
    https://www.quora.com/Does-inheritance-affect-run-time-performance-in-C++-1   
    
* 이동 생성자  
    https://link2me.tistory.com/1756   
    
* 왜 언리얼은 굳이 STL 대신 자체 라이브러리를 구현할까?  
    https://stackoverflow.com/questions/64158032/why-do-big-projects-like-unreal-engine-write-their-own-container-classes   
    
* modern c++에서의 using 키워드  
    * using을 통해 typedef가 가능  
        * https://stackoverflow.com/questions/10747810/what-is-the-difference-between-typedef-and-using-in-c11  
    * https://jungmonster.tistory.com/323  
    
* boost c++ 라이브러리  
    * https://namu.wiki/w/Boost  
    
* new, delete 연산자는 오버로딩이 가능하며, malloc, free를 이용해 자체 구현이 가능. 만약 모든 new, delete를 변경하는 게 아닌 특정 클래스 생성에만 적용되게 하려면 클래스 내에서 연산자 오버로딩을 해주면 된다.  (iocp 29참조)  
* 이미 확보된 메모리에 생성자를 수동으로 호출해주는 법 - placement new (new x; 꼴이 아니라 new(myMem)x(); 형태)  

* template<typename... Args>  

* rvalue vs lvalue  
  https://assortrock.com/236  
  
* std::set의 내부 비교연산을 처리하는 comparator (템플릿 인자로 받음) 및 이를 어떤 식으로 활용할 수 있는지에 대하여  
  https://chanhuiseok.github.io/posts/algo-46/  
