# JAVA 
## Типы данных
1. Ссылочные 
2. Примитивные:
    - boolean
    - int
    - short (целое малое число)
    - long
    - float
    - double
    - Char (единичный символ)
```java
class Program {
    public static void main(String[] args) {
        float e = 2.7f; //обязательно f
        double = pi = 3.1414;
        System.out.println(e); //2.7
        System.out.println(pi); // 3.1415

        boolean f = true & false;
        f = true ^ false //дизъюнкция

        var i = 123; // неявная типизация

        String s = "querty";
        s.charAt(1) // выведет символ под индексом 1

    }
}
```
## Обьявление переменной
<тип><индентификатор>;   
<индентификатор> = <значение>;  

## Операции Java
- присваивание - `=`
- арифметические: `*`, `/`, `+`,`-`, `%`, `++`, `--`
- операции сравнения: `<`, `>`, `==`, `!`, `>=`, `<=`
- логические операции: `||`, `&&`, `^`, `!`
- побитовые операции: `<<`, `>>` (побитовые сдвиги), `&`, `|`, `^`

```java
class Program {
    public static void main(String[] args) {
    int a = 123;
        System.out.println(a++) // постфиксный инкремент (приоритет операции ниже)

        System.out.println(++a) // префиксный инкремент (приоритет операции выше)
    }
}        

```

## Массивы
```java
class Program {
    public static void main(String[] args) {
        int[] arr = new int[10];
        System.out.println(arr.length); // 10
        arr = new int[] {1, 2, 3, 4, 5}; 
        System.out.println(arr.length); // 5


        int[][] arr = new int[3][5];
        for (int i=0; i<arr.length; i++) {
            for (int j=0; j < arr[i].length; j++) {
                System.out.println('%d', arr[i].length);
            }    
        }
    }
} 
```
## Преобразование 
```java
class Program {
    public static void main(String[] args) {
        int i = 123; double d = i;
        System.out.println(i); // 123
        System.out.println(d); // 123.0

        d = 3.1415; i = int(d)
        System.out.println(d); // 3.1415
        System.out.println(i); // 3

        d = 3.9415; i = int(d);
        System.out.println(d); // 3.9415
        System.out.println(i); // 3

        byte b = Byte.parseByte("123");
        System.out.println(b); // 123

        b = Byte.parseByte("1234");
        System.out.println(b); // NumberFormatException: Value out of range

    }
} 
```

## Получение данных от пользователя
```java 
import java.util.Scanner;
class Program {
    public static void main(String[] args) {
        Scanner iScanner = new Scanner(System.in);
        System.out.printf("name: ");
        String name = iScanner.nextLine();
        System.out.printf("Привет, %s!", name);
        iScanner.close();

    }
}
```

## Спецификаторы
`%d` - целочисленные значения;   
`%x` - для вывода шестнадцатеричных чисел;   
`%f` - для вывода чисел с плавающей точкой;   
`%e` - для вывода чисел в экспоненцильной форме (например 3,1415е+01);   
`%c` - для вывода одиночного символа;   
`%s` - для вывода строковых значений.

## Функции, методы
```java 
class Program {
    public static void main(String[] args) {
       sayHi(); 

    }

    static void sayHi(){
        System.out.println("Привет!");
    }

    static int sum(int a, int b) {
        return a + b;
    }
}
```

## Управляющие конструкции
```java 
class Program {
    public static void main(String[] args) {
        int a = 1;
        int b = 2;
        int c;
        if (a > b) {
            c = a;
        } else {
            c = b;
        }
        System.out.println(c);

        //Тернарный оператор
        int min = a < b ? a : b;
        System.out.println(min);


        // Оператор выбора

        int mounth = value;
        String text = "";
        switch (mounth) {
            case 1:
                text = "Autumn";
                break;
            ...
            default:
                text = "mistake";
                break;    
        }
        System.out.println(text)
        iScanner.close()

    // Циклы
    // while
        int value = 321;
        int count = 0;
        while (value != 0) {
            value /=10;
            count++;
        }
        System.out.println(count);
    //do while
        do {
            value /=10;
            count++;
        } while (value != 0);   
        System.out.println(count);
    // for (for in)

        int[] arr = int[]{1, 2, 3}

        for (int item: arr) {
            System.out.println(item); // невозможно работать с итерируемыми обьектами коллекции
        }
    }
}
```

## Работа с файлами
### Создание и запись/дозапись

```java 
import java.io.FileWriter;
import java.io. IOException;

class Program {
    public static void main(String[] args) {
        try (FileWriter fw = new FileWriter("file.txt", false)) {
            fw.write("line_1");
            fw.append('\n');
            fw.append("2");
            fw.append("\n");
            fw.write("line_3");
            fw.flush();
        } catch (IOException ex) {
            System.out.println(ex.getMessage()); // обработка ошибок
        }
    }
}

```

### Чтение, Вариант посимвольно

```java 
import java.io.*;

class Program {
    public static void main(String[] args) throws Exception {
        FileReader fr = new FileReader("file.txt");
        int c;
        while ((c = fr.read()) != -1) {
            char ch = (char) c;
            if (ch == '\n') {
                System.out.print(ch);
            } else {
                System.out.print(ch);
            }
        }
    }
}

```



