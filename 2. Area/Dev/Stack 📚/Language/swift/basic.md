
* 2024-07-15 
	https://www.youtube.com/watch?v=qWA04z_4Okk
	* 세미콜론 없음
	* 타입을 지정해줄 수 있다 -> 스크립트 언어가 떠오른다. var name : String = "yourname"
	* 사용이 용이한 듯.
	* 플레이그라운드를 지원해줘서 쉽게 언어를 실험해볼 수 있는 환경이 구축되어 있다.
	* 다양한 애플 생태계 개발을 지원한다.
	* xcode -> playground -> blank 템플릿 지정
	* LiveView 를 지원하기에 따로 compile, build 필요가 없다

Java 에선 자료형을 int, long, double, float, char, String, boolean ... 을 사용했다. 
Swift 에선 Int, Double, Bool, Character, String 으로 대문자를 붙혀서 사용하는 듯. 

변수는 var, 상수는 let 을 사용한다. 

	var number: Int = 10
	var pi: Double = 3.14 
	var isTrue: Bool = true
	var letter: Character ="A" // 문자여도 큰 따옴표를 사용한다.
	var text: String = "Hello World"

if 조건문에 괄호가 필요없다. 

	if(age>18){ // Java 스타일
		System.out.println("Adult"); 
	} 
	
	if age > 18 { // Swift 스타일
		print("Adult")
	}

for 반복문도 괄호가 필요없고 인덱싱 시 0..<5 와 같이 사용한다. 

	for(int i=0; i<5; i++) // Java 스타일
		System.out.println(i);

	for i in 0..<5 {
		print(i)
	}

함수선언은 func 키워드를 사용한다. 

	public int add(int a, int b){ // Java 스타일 
		return a + b;
	}

	func add(_a: Int, _b : Int) -> Int { // Swift 스타일
	return a+b
	}

클래스 선언은 class 키워드를 사용한다. 

	public class Person { // Java 스타일
		String name; 
		
		public person(String name){
				this.name = name;
		}

		public String getName(){
			return name;
		}
		
		public void setName(String name){
			this.name = name;
		}
	}
	
	Person person = new Person("YoungseopLee"); 

	class Person { // Swift 스타일
		var name: String
		
		init(name: String){
			self.name = name
		}
		
		func getName() -> String {
			return name
		}
		
		func setName(name: String){
			self.name = name
		}
	}

