# lombok
## lombok 이란?
-  Java에서 반복적인 코드 작성을 줄이기 위해 사용하는 라이브러리.
- 특히, Getter, Setter, toString, Equals, HashCode 메서드 등을 자동으로 생성해 줌으로써 코드의 간결성과 가독성을 높이는 데 유용함. 
- Lombok은 주석(Annotation)을 사용해 다양한 기능을 제공하며, 이를 통해 많은 수작업 코드를 대체할 수 있음.

## lombok의 주요 기능
### 1. @Getter, @Setter
- 클래스 필드에 대한 getter(읽기 기능)/ setter(수정 기능) 메서드를 자동으로 생성함

```java
// 사용 예시
@Getter 
@Setter
public class User{
    private String name;    // User 클래스의 name과 age 필드에 대한
    private int age;        // getter와 setter 메서드가 자동으로 생성
}

// 생성되는 메서드
public String getName() {
    return name;
}

public void setName(String name) {
    this.name = name;
}

public int getAge() {
    return age;
}

public void setAge(int age) {
    this.age = age;
}

```

### 2. @ToString
- toString() 메서드를 자동으로 생성함
- toString() 메서드는 객체를 문자열로 표현할 때 주로 사용되며, 디버깅 또는 객체를 출력할 때 유용.

```java
// 사용 예시 
@ToString   // User 객체를 출력할 때 자동으로 name과 age 필드값을 포함한 문자열을 반환하는 메서드 생성
pulbic class User{
    private String name;
    private int age;
}

// 생성되는 메서드
@Override
public String toString() {
    return "User(name=" + name + ", age=" + age + ")";
}
```

### 3. @NoArgsConstructor, @AllArgsConstructor, @RequiredArgsConstructor
- @NoArgsConstructor
    - 파라미터가 없는 기본 생성자를 자동으로 생성.
    - 기본 생성자는 매개변수 없이 객체를 생성할 때 유용함.

    ```java
    //사용 예시
    @NoArgsConstructor
    public class User {
        private String name;
        private int age;
    }

    // 생성된느 기본 생성자
    public User() {}
    ```

- @AllArgsConstructor
    - 모든 필드를 포함한 생성자를 자동으로 생성. 
    - 이 생성자는 모든 필드에 대한 값을 전달받아 객체를 초기화할 때 유용함.
    
    ```java
    // 사용 예시
    @AllArgsConstructor
    public class User {
        private String name;
        private int age;
    }

    // 생성되는 생성자
    public User(String name, int age) {
    this.name = name;
    this.age = age;
    }
    ```

- @RequiredArgsConstructor
    - final 필드나 @NonNull로 표시된 필드만을 포함하는 생성자를 자동으로 생성. - 반드시 초기화해야 할 필드만 포함한 생성자를 제공할 때 유용합니다.

    ```java
    // 사용 예시
    @RequiredArgsConstructor
    public class User {
        @NonNull private String name;
        private final int age;
    }
    
    // 생성되는 생성자
    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }
    ```

### 4. @Data
- @Getter, @Setter, @ToString, @EqualsAndHashCode, @RequiredArgsConstructor 어노테이션들을 한 번에 적용하는 종합 어노테이션
- 이 하나의 어노테이션으로 필드에 대한 기본적인 메서드들을 모두 자동으로 생성할 수 있음.

```java
// 사용 예시
@Data // lombok은 getter/setter/toString()/equals()/hashCode()/필수 생성자등을 자동으로 생성
public class User {
    private String name;
    private int age;
}
```

### 5. @Builder
- 빌더 패턴을 간편하게 구현할 수 있게 해줌.
- 빌더 패턴은 객체 생성 시 여러 매개변수를 보다 직관적이고 유연하게 처리할 수 있도록 도와줌

```java
// 사용 예시
// user.builer() 메서드를 통해 객체를 생성할 수 있음
// 각 필드에 값을 유연하게 설정할 수 있음
@Builder    
public class User {
    private String name;
    private int age;
}

// 객체 생성 예시
User user = User.builder().name("John").age(25).build();
```
