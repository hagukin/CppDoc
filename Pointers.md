* 포인터의 구조와 원리 + 포인터 형변환이 처리되는 과정  
https://stackoverflow.com/questions/17260527/what-are-the-rules-for-casting-pointers-in-c  
* 객체 내부에서 자기 자신에 대한 shared_ptr를 사용하는 방법  
```c++
// 잘못된 방법
class A
{
	// ...
	shared_ptr<A> a;
	
	a = this; // 에러, this는 shared_ptr<A>가 아니라 A*임
	a = shared_ptr<A>(a); // 에러는 안나지만 심각한 결과를 초래함. shared_ptr가 두개 만들어짐, 고로 ref count를 따로 세게 되어 한쪽이 지워졌지만 다른쪽은 남아있는 상황 등이 발생할 수 있음
}

// 올바른 방법
class A : public enable_shared_from_this<A>
{
	// ...
	shared_ptr<A> a;
	
	a = shared_from_this(); // 내부적으로는 weak_ptr를 사용
}
```  
* void pointer
전반적으로 컴파일러마다 구현에 편차가 많다, C에서 generic function을 구현할 때 템플릿 대신 사용된다.  
https://www.geeksforgeeks.org/void-pointer-c-cpp/  
```c++
int a = 10;
void* ptr = &a;
cout << *ptr; // 에러
cout << *(int*)ptr; // Fine!
```
