# fmt 패키지를 이용한 텍스트 입출력
<br>
<br>

### fmt패키지

표준 입출력 기능은 Go언어 기본 패키지인 fmt에서 제공합니다. GO언어는 자주 사용하는 기능을 묶어서 패키지로 제공합니다.

패키지를 사용하려면 import를 사용해서 사용할 패키지를 불러와야 한다.

<br>
<br>

```go
import "fmt"
```

<br>
<br>

**fmt 패키지는 3가지 표준 출력용 함수를 제공한다.**

| Print() | 함수 입력값들을 출력한다. |
| --- | --- |
| Println() | 함수 입력값들을 출력하고 개행한다. |
| Printf() | 서식(format)에 맞도록 입력값들을 출력한다. |

<br>
<br>

### 표준 입력

표준 입력은 표준 입력 장치에서 데이터를 얻어옵니다. 일반적으로 표준 입력을 변경하지 않았다면 키보드가 표준 입력 장치다. fmt패키지는 표준 입력으로부터 입력받는 Scan(), Scanf(), Scanln() 함수를 제공

| Scan() | 표준 입력에서 값을 입력받는다. |
| --- | --- |
| Scanf() | 표준 입력에서 서식 형태로 값을 입력받는다. |
| Scanln() | 표준 입력에서 한 줄을 읽어서 값을 입력받습니다. |

<br>
<br>

**Scan()**

Scan()함수는 값을 채워넣을 변수들의 메모리 주소를 인수로 받는다.(enter키도 공란으로 인식한다.)

```go
func Scan(a ... interface{}) (n int, err error)
```
<br>

예제코드

```go
package main

import "fmt"

func main() {
	var a int
	var b int

	n, err := fmt.Scan(&a, &b)
	if err != nil {
		fmt.Println(n, err)
	} else {
		fmt.Println(n, a, b)
	}
}
```
<br>
<br>

**Scanf()**

Scanf()함수는 서식에 맞춘 입력을 받습니다.

```go
func Scanf(format string, a ... interface{}) (n int, err error)
```

<br>
예제 코드

```go
package main

import "fmt"

func main() {
	var a int
	var b int

	n, err := fmt.Scanf("%d %d\n", &a, &b)
	if err != nil {
		fmt.Println(n, err)
	} else {
		fmt.Println(n, a, b)
	}
}
```

<br>
<br>

Scanln()

Scanln()함수는 한 줄을 입력받아서 인수로 들어온 변수 메모리 주소에 값을 채워줍니다.

```go
func Scanln(a ... interface{}) (n int, err error)
```

<br>
예제코드

```go
package main

import "fmt"

func main() {
	var a int
	var b int

	n, err := fmt.Scanln(&a, &b)
	if err != nil {
		fmt.Println(n, err)
	} else {
		fmt.Println(n, a, b)
	}
}
```

<br>
<br>

---

### 핵심 요약

1. fmt 패키지를 이용해서 데이터를 표준 입출력 할 수 있다.
2. 표준 입출력 함수로는 Print(), Printf(), Println()이 있다.
3. 서식 문자를 이용하면 다양한 형식으로 출력할 수 있다. 최소 출력 너비와 소숫점 이하 숫자 개수를 지정할 수 있다.
4. 서식 문자 %v를 사용하면 모든 타입의 기본 서식으로 출력한다.
5. 표준 입력 함수로는 Scan(), Scanf(), Scanln()이 있다.
6. 입력 받을 때 에러가 발생하면 표준 입력 스트림을 지웁시다.