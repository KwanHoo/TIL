# _Java Beans_

## 자바 빈즈

- Build Tool에서 시각적으로 조작할 수 있는 재사용 가능한, 자바로 작성된 소프트웨어 컴포넌트
- 현재 실행되고 있는 JVM 프로세스 내에서 실행되고 있는 인스턴스이며 이 중 어떤 인스턴스들은 필요에 따라 내가 호출하여 사용할 수 있음
- 자바로 작성한 자바 클래스 중에 자바 빈즈 컨벤션(Java Beans Convention)에 맞게 작성된 클래스를 JSP에서 사용가능
- EJB(Enterprise Java Beans)와는 다른것

## 자바 빈즈 사용 목적

- JSP 페이지의 로직 부분을 분리해서 코드를 재사용함으로 프로그램의 효율을 높임
- 프로그램의 모듈화(component)는 코드를 재사용함으로 프로그램의 작성 기간이 단축되고, 이미 실 시스템에 사용했던 코드를 사용하므로 코드의 안정성이 보장되며 유지 보수가 쉬움

## 자바 빈즈 컨벤션

1. 자바빈은 기본(default)패키지 이외의 특정 패키지에 속해 있어야함
2. 클래스는 인자(argument)가 없는 기본 생성자(dafault constructor)를 갖음
3. 클래스의 멤버 변수는 프로퍼티(properties)라고 하며 private 접근 제한자를 가져야함
4. 클래스의 프로퍼티들은 Getter/Setter를 통해 접근할 수 있어야 함
   - Getter/Setter의 접근 제한자는 public이어야 함
   - Getter의 이름은 get{프로퍼티 이름} 이며, Setter의 이름은 set{프로퍼티 이름}dla
   - Read Only 인 경우 Setter는 없을 수 있음
   - Getter의 경우 파라미터가 존재하지 않아야 하며, setter의 경우 하나 이상의 파라미터가 존재함
5. 프로퍼티의 타입이 Bollean인 경우 is로 시작할 수 있음

## 자바 빈즈 예제

```
class PersonBean implements java.io.Serializable {

	private static final long serialVersionUID = 1L;
	private String name;
	private boolean coding;

	// 기본 생성자
	public PersonBean() {}

	public String getName() {
		return this.name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public boolean isCoding() {
		return this.coding;
	}

	public void setCoding(boolean coding) {
		this.coding = coding;
	}
}

public class TestPersonBean {
	public static void main(String[] args) {

		PersonBean person = new PersonBean();
		person.setName("Bob");
		person.setCoding(true);

		System.out.print(person.getName());
		System.out.println(person.isCoding() ? " [coding]" : ""); //Bob [coding]
	}
}
```

[참고 포스팅](https://velog.io/@imok-_/%EC%9E%90%EB%B0%94-%EB%B9%88%EC%A6%88Java-Beans%EB%9E%80)
