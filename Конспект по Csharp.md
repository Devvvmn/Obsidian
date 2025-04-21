🧠 Структура и порядок выполнения программы

- Выполнение сверху вниз: Программа на C# выполняется построчно, начиная с верхней части кода и двигаясь вниз. Компилятор преобразует ваш код в инструкции, которые процессор может понять и выполнить.
    
- Инструкции завершаются `;`: Каждая инструкция в C# должна заканчиваться точкой с запятой. Это говорит компилятору, где заканчивается одна команда и начинается другая.
    
- Точка входа: `Main()` в классе `Program`. Это специальный метод, с которого начинается выполнение любой консольной программы на C#. Он находится внутри класса `Program`.
    
    - Пример:
        
        ```csharp
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Hello, World!");
            }
        }
        ```
        
- Комментарии:
    
    - `//` (однострочные): Все, что находится после `//` до конца строки, игнорируется компилятором.
        
        ```csharp
        // Это однострочный комментарий.
        Console.WriteLine("Hello"); // Это тоже комментарий.
        ```
        
    - `/* ... */` (многострочные): Все, что находится между `/*` и `*/`, игнорируется компилятором. Это удобно для больших блоков текста.
        
        ```csharp
        /*
            Это
            многострочный
            комментарий.
        */
        ```
        

🔠 Типы данных

- Примитивные: Это основные, встроенные типы данных C#.
    
    - `int`: Целое число (например, 10, -5, 0).
        
    - `float`: Число с плавающей запятой одинарной точности (например, 3.14f, -2.7f). Суффикс `f` обязателен.
        
    - `double`: Число с плавающей запятой двойной точности (например, 3.14159, -12.34). Это тип по умолчанию для литералов с плавающей запятой.
        
    - `char`: Один символ Unicode (например, 'a', 'Z', 'ö').
        
    - `bool`: Логическое значение (`true` или `false`).
        
- Строки:
    
    - `string`: Представляет последовательность символов (например, "Hello", "World"). `string` не является примитивным типом, но часто рассматривается как таковой из-за частого использования.
        
- Модификаторы: Используются с целочисленными типами для указания размера хранилища.
    
    - `byte`: 8-битное целое число без знака (от 0 до 255).
        
    - `short`: 16-битное целое число со знаком (от -32,768 до 32,767).
        
    - `long`: 64-битное целое число со знаком (очень большие числа).
        
    - `decimal`: 128-битное число, предназначенное для финансовых расчетов. Имеет большую точность, но меньший диапазон, чем `double`. Суффикс `m` обязателен (например, 19.99m).
        
- Преобразования:
    
    - `Convert`: Преобразует значение одного типа в другой. Может выбрасывать исключения, если преобразование не удается.
        
        ```csharp
        int num = Convert.ToInt32("123");
        ```
        
    - `Parse`: Преобразует строку в числовой тип. Выбрасывает исключение, если строка не является допустимым числом.
        
        ```csharp
        int num = int.Parse("456");
        ```
        
    - `TryParse`: Пытается преобразовать строку в числовой тип. Возвращает `true`, если преобразование удалось, и `false` в противном случае. Не выбрасывает исключений.
        
        ```csharp
        int num;
        bool success = int.TryParse("789", out num);
        if (success)
        {
           Console.WriteLine(num);
        }
        else
        {
           Console.WriteLine("Conversion failed.");
        }
        ```
        

🧾 Переменные

- Объявление: `тип имя = значение;` Выделяет память для хранения значения указанного типа и связывает эту память с именем переменной.
    
    - Пример:
        
        ```csharp
        int age = 30;
        string name = "Alice";
        ```
        
- Инициализация: `int a; a = 10;` Присваивает переменной начальное значение. Объявление и инициализацию можно разделить.
    
- Вывод типа: `var`. Позволяет компилятору определить тип переменной на основе присвоенного значения. Может использоваться только внутри методов.
    
    - Пример:
        
        ```csharp
        var message = "Hello"; // message будет иметь тип string
        var count = 100;       // count будет иметь тип int
        ```
        

⌨️ Ввод и вывод

- Вывод: `Console.WriteLine()`. Выводит текст в консоль и добавляет символ новой строки в конце. `Console.Write()` выводит текст без добавления новой строки.
    
    - Пример:
        
        ```csharp
        Console.WriteLine("This is a line.");
        Console.Write("This is ");
        Console.Write("continued.");
        ```
        
- Ввод: `Console.ReadLine()`. Читает строку текста из консоли. Возвращает `string`.
    
- Преобразование: `int.Parse(Console.ReadLine())`. Часто используется для преобразования ввода пользователя (который всегда является строкой) в числовой тип.
    
    - Пример:
        
        ```csharp
        Console.Write("Enter your age: ");
        string input = Console.ReadLine();
        int age = int.Parse(input);
        Console.WriteLine($"Your age is: {age}");
        ```
        

🔁 Операторы и условия

- Арифметические:
    
    - `+`: Сложение.
        
    - `-`: Вычитание.
        
    - `*`: Умножение.
        
    - `/`: Деление. Если оба операнда целые числа, результат будет целым числом (без остатка).
        
    - `%`: Остаток от деления (модуль).
        
- Логические:
    
    - `&&`: Логическое И (AND). Возвращает `true`, если оба операнда `true`.
        
    - `||`: Логическое ИЛИ (OR). Возвращает `true`, если хотя бы один операнд `true`.
        
    - `!`: Логическое НЕ (NOT). Инвертирует значение операнда.
        
- Сравнение:
    
    - `==`: Равно.
        
    - `!=`: Не равно.
        
    - `>`: Больше.
        
    - `<`: Меньше.
        
    - `>=`: Больше или равно.
        
    - `<=`: Меньше или равно.
        
- Условия:
    
    - `if`: Выполняет блок кода, если условие истинно.
        
    - `else if`: Проверяет другое условие, если предыдущее условие ложно.
        
    - `else`: Выполняет блок кода, если ни одно из предыдущих условий не истинно.
        
        ```csharp
        if (age >= 18)
        {
            Console.WriteLine("Adult");
        }
        else if (age >= 13)
        {
            Console.WriteLine("Teenager");
        }
        else
        {
            Console.WriteLine("Child");
        }
        ```
        
    - `switch`: Выбирает один из нескольких блоков кода для выполнения на основе значения переменной.
        
        ```csharp
        switch (day)
        {
            case 1:
                Console.WriteLine("Monday");
                break;
            case 2:
                Console.WriteLine("Tuesday");
                break;
            default:
                Console.WriteLine("Other day");
                break;
        }
        ```
        

🔁 Циклы

- Типы:
    
    - `while`: Выполняет блок кода, пока условие истинно. Проверяет условие _перед_ выполнением блока.
        
        ```csharp
        int i = 0;
        while (i < 5)
        {
            Console.WriteLine(i);
            i++;
        }
        ```
        
    - `do while`: Выполняет блок кода, пока условие истинно. Проверяет условие _после_ выполнения блока. Блок выполняется хотя бы один раз.
        
        ```csharp
        int i = 0;
        do
        {
            Console.WriteLine(i);
            i++;
        }
        while (i < 5);
        ```
        
    - `for`: Выполняет блок кода заданное количество раз. Имеет инициализацию, условие и итератор.
        
        ```csharp
        for (int i = 0; i < 5; i++)
        {
            Console.WriteLine(i);
        }
        ```
        
- Управление:
    
    - `break`: Выходит из цикла немедленно.
        
    - `continue`: Переходит к следующей итерации цикла, пропуская оставшуюся часть текущей итерации.
        
- Особенности:
    
    - Вложенные циклы: Цикл внутри другого цикла.
        
        ```csharp
        for (int i = 0; i < 3; i++)
        {
            for (int j = 0; j < 2; j++)
            {
                Console.WriteLine($"i: {i}, j: {j}");
            }
        }
        ```
        
    - Обратные циклы: Цикл, который считает в обратном направлении.
        
        ```csharp
        for (int i = 10; i > 0; i--)
        {
            Console.WriteLine(i);
        }
        ```
        
    - Несколько переменных и условий: Можно использовать более сложные условия и несколько переменных в циклах (особенно в `for`).
        

❓ Тернарный оператор

- Синтаксис: `var result = условие ? значение1 : значение2;` Краткая форма для `if-else`, когда нужно присвоить значение переменной.
    
    - Пример:
        
        ```csharp
        int age = 20;
        string message = (age >= 18) ? "Adult" : "Not adult";
        Console.WriteLine(message); // Выведет "Adult"
        ```
        

🧩 Массивы

- Одномерные: `int[] arr = new int[5];` Создает массив из 5 целых чисел. Индексы начинаются с 0.
    
- Инициализация: `new int[] {1, 2, 3}`. Создает и инициализирует массив с указанными значениями. Размер определяется количеством элементов. Можно опустить `new int[]` и просто написать `{ 1, 2, 3 }`
    
- Перебор:
    
    - `for`: Используется для перебора элементов массива по индексу.
        
        ```csharp
        int[] numbers = { 10, 20, 30 };
        for (int i = 0; i < numbers.Length; i++)
        {
            Console.WriteLine(numbers[i]);
        }
        ```
        
    - `foreach`: Упрощает перебор всех элементов массива.
        
        ```csharp
        int[] numbers = { 10, 20, 30 };
        foreach (int number in numbers)
        {
            Console.WriteLine(number);
        }
        ```
        
- Многомерные: Массивы с более чем одним измерением.
    
    - `int[,] arr = new int[3, 3];` Создает двумерный массив 3x3.
        
- Ступенчатые: Массивы массивов, где каждый подмассив может иметь разную длину.
    
    - `int[][] jagged = new int[3][];` Создает массив из 3 элементов, где каждый элемент является массивом целых чисел. Подмассивы нужно создавать отдельно.
        
        ```csharp
        int[][] jagged = new int[3][];
        jagged[0] = new int[] { 1, 2, 3 };
        jagged[1] = new int[] { 4, 5 };
        jagged[2] = new int[] { 6, 7, 8, 9 };
        ```
        
- Индексы и диапазоны:
    
    - `arr[^1]`: Доступ к последнему элементу массива (индекс с конца).
        
    - `arr[1..3]`: Создает диапазон, включающий элементы с индекса 1 до индекса 2 (не включая 3). `..` - это оператор диапазона.
        

🛠️ Методы

- Объявление:
    
    ```csharp
    void SayHello(string name)
    {
        Console.WriteLine($"Привет, {name}");
    }
    ```
    
    - `void`: Указывает, что метод не возвращает никакого значения.
        
    - `SayHello`: Имя метода.
        
    - `string name`: Параметр метода (входные данные).
        
    - `Console.WriteLine(...)`: Тело метода (код, который выполняется при вызове метода).
        
- Возврат значений: `int Sum(int a, int b) => a + b;` Метод возвращает значение типа `int`. `=>` - это краткая форма для метода с одним выражением.
    
    - Пример:
        
        ```csharp
        int result = Sum(5, 3); // result будет равно 8
        ```
        
- Перегрузка: Определение нескольких методов с одинаковым именем, но разными параметрами (разное количество или типы). Компилятор выбирает правильный метод на основе аргументов, переданных при вызове.
    
    - Пример:
        
        ```csharp
        int Sum(int a, int b) => a + b;
        double Sum(double a, double b) => a + b;
        int Sum(int a, int b, int c) => a + b + c;
        
        Console.WriteLine(Sum(1, 2));       // Вызов int Sum(int, int)
        Console.WriteLine(Sum(1.5, 2.5));   // Вызов double Sum(double, double)
        Console.WriteLine(Sum(1, 2, 3));    // Вызов int Sum(int, int, int)
        ```
        

🧱 Область видимости

- Локальные переменные: Объявлены внутри метода. Доступны только внутри этого метода.
    
    - Пример:
        
        ```csharp
        void MyMethod()
        {
            int x = 10; // x - локальная переменная
            Console.WriteLine(x);
        }
        // Console.WriteLine(x); // Ошибка: x не существует вне MyMethod
        ```
        
- Глобальные переменные: Объявлены внутри класса, но за пределами любого метода. Они называются полями класса. Доступны для всех методов класса.
    
    - Пример:
        
        ```csharp
        class MyClass
        {
            int y = 20; // y - глобальная переменная (поле)
        
            void MyMethod1()
            {
                Console.WriteLine(y);
            }
        
            void MyMethod2()
            {
                Console.WriteLine(y);
            }
        }
        ```
        
- Перекрытие переменных: Если локальная переменная имеет то же имя, что и глобальная переменная, локальная переменная "перекрывает" глобальную внутри метода.
    
    - Пример:
        
        ```csharp
        class MyClass
        {
            int z = 30;
        
            void MyMethod()
            {
                int z = 40; // Локальная переменная z перекрывает глобальную z
                Console.WriteLine(z); // Выведет 40
                Console.WriteLine(this.z); // доступ к глобальной переменной z  через this
            }
        }
        ```
        

📦 Ссылочные и значимые типы

- Значимые: Хранят фактическое значение непосредственно в памяти, выделенной для переменной. При присваивании или передаче аргумента создается _копия_ значения.
    
    - Примеры: `int`, `float`, `double`, `char`, `bool`, `struct`, `enum`.
        
    - Размещение: Обычно хранятся в стеке (более быстрое выделение памяти).
        
- Ссылочные: Хранят _ссылку_ (адрес) на место в памяти, где хранятся данные. При присваивании или передаче аргумента копируется _ссылка_, а не сами данные. Обе переменные теперь указывают на один и тот же объект в памяти.
    
    - Примеры: `string`, `class`, `array`, `interface`, `delegate`.
        
    - Размещение: Данные хранятся в куче (более гибкое, но медленное выделение памяти).
        
- Разница на примере:
    
    ```csharp
    // Значимый тип (int)
    int a = 5;
    int b = a; // b получает копию значения a (5)
    b = 10;    // a не меняется
    Console.WriteLine(a); // Выведет 5
    Console.WriteLine(b); // Выведет 10
    
    // Ссылочный тип (массив)
    int[] arr1 = { 1, 2, 3 };
    int[] arr2 = arr1; // arr2 получает копию *ссылки* на arr1
    arr2[0] = 100;    // Изменяется элемент *в том же* массиве, на который ссылаются arr1 и arr2
    Console.WriteLine(arr1[0]); // Выведет 100
    Console.WriteLine(arr2[0]); // Выведет 100
    ```
    

⛔ Null и связанные операторы

- `null`: Представляет отсутствие значения. Может быть присвоен только ссылочным типам и Nullable
    
- Оператор объединения: `??`. Возвращает левый операнд, если он не равен `null`; в противном случае возвращает правый операнд.
    
    - Пример:
        
        ```csharp
        string name = null;
        string defaultName = "Unknown";
        string actualName = name ?? defaultName; // actualName будет "Unknown"
        ```
        
- Присваивание с объединением: `??=`. Присваивает левому операнду значение правого операнда, только если левый операнд равен `null`.
    
    - Пример:
        
        ```csharp
        string name = null;
        name ??= "John"; // name станет "John"
        Console.WriteLine(name);
        
        string city = "New York";
        city ??= "Los Angeles";  // city не изменится
        Console.WriteLine(city);
        ```

📚 Конспект по C#

- **Оператор присваивания объединения со значением NULL ??=**
    
    - Присваивает значение переменной, только если она равна null.
        
    - `string name = null; name ??= "John"; // name теперь "John"`
        
    - Полезно для установки значений по умолчанию, если переменная еще не инициализирована.
        
          
        
        Пример:
        
        ```
        string? greeting = null;
        greeting ??= "Hello, User!";
        Console.WriteLine(greeting); // Выведет "Hello, User!"
        
        string? existingGreeting = "Welcome back!";
        existingGreeting ??= "Another greeting";
        Console.WriteLine(existingGreeting); // Выведет "Welcome back!"
        ```
        
        Этот оператор как бы говорит: "Если переменная слева равна null, присвой ей значение справа".
        
- **Оператор условного NULL ?.**
    
    - Позволяет безопасно обращаться к членам объекта, если он не null.
        
    - `string s = null; int? length = s?.Length; // length будет null`
        
    - Избегает исключения NullReferenceException.
        
          
        
        Пример:
        
        ```
        string? message = null;
        //int length = message.Length; //  NullReferenceException
        int? safeLength = message?.Length;
        Console.WriteLine($"Length: {safeLength}"); // Выведет "Length: "
        ```
        
        Вместо того, чтобы бросать исключение, оператор ?. возвращает null, если объект равен null. Это делает код чище и безопаснее.
        
- **Ключевое слово ref**
    
    - Передача аргумента по ссылке, изменения внутри метода влияют на оригинал.
        
    - `void Change(ref int x) { x = 10; } int a = 5; Change(ref a); // a теперь 10`
        
    - Полезно, когда метод должен изменить значение переменной, переданной ему.
        
          
        
        Пример:
        
        ````
        void Increment(ref int number)
        {
            number++;
            Console.WriteLine($"Number inside method: {number}"); // Выведет 6
        }
        
        int myNumber = 5;
        Increment(ref myNumber);
        Console.WriteLine($"Number outside method: {myNumber}"); // Выведет 6
        ```ref` позволяет методу напрямую работать с исходной переменной, а не с её копией.
        ````
        
- **Ключевое слово out**
    
    - Передача аргумента по ссылке, но переменная должна быть присвоена внутри метода.
        
    - `void GetValue(out int x) { x = 20; } int b; GetValue(out b); // b теперь 20`
        
    - Используется, когда метод должен вернуть несколько значений.
        
          
        
        Пример:
        
        ````
        void Divide(int a, int b, out int quotient, out int remainder)
        {
            quotient = a / b;
            remainder = a % b;
        }
        
        int result;
        int остаток;
        Divide(10, 3, out result, out остаток);
        Console.WriteLine($"Quotient: {result}, Remainder: {остаток}"); // Выведет "Quotient: 3, Remainder: 1"
        ```out` особенно полезен, когда нужно вернуть из метода не одно, а несколько значений.
        ````
        
- **Модификатор in**
    
    - Передача аргумента по ссылке для чтения, запрещает изменение аргумента внутри метода.
        
    - `void Display(in int x) { Console.WriteLine(x); } int c = 30; Display(in c);`
        
    - Оптимизация производительности, особенно при передаче больших структур.
        
          
        
        Пример:
        
        ```
        void PrintPerson(in Person person)
        {
            Console.WriteLine($"Name: {person.Name}, Age: {person.Age}");
            // person.Age = 31; // Ошибка!  Нельзя изменять in-параметр
        }
        
        struct Person
        {
            public string Name;
            public int Age;
        }
        
        Person myPerson = new Person { Name = "Bob", Age = 30 };
        PrintPerson(in myPerson); // Выведет "Name: Bob, Age: 30"
        ```
        
        Модификатор `in` говорит компилятору, что метод не будет менять переданный аргумент, что позволяет делать небольшие оптимизации.
        
- **Ключевое слово params**
    
    - Позволяет передавать переменное количество аргументов одного типа в метод.
        
    - `int Sum(params int[] numbers) { ... } Sum(1, 2, 3); Sum(4, 5, 6, 7);`
        
    - Удобно для создания методов с гибким числом аргументов.
        
          
        
        Пример:
        
        ```
        int Sum(params int[] numbers)
        {
            int sum = 0;
            foreach (int number in numbers)
            {
                sum += number;
            }
            return sum;
        }
        
        int total1 = Sum(1, 2, 3);
        int total2 = Sum(5, 10, 15, 20);
        Console.WriteLine($"Sum1: {total1}, Sum2: {total2}"); // Выведет "Sum1: 6, Sum2: 50"
        ```
        
        Теперь не нужно создавать массив перед вызовом метода, можно просто перечислить значения через запятую.
        
- **Необязательные параметры метода**
    
    - Параметры с значениями по умолчанию, можно не передавать при вызове метода.
        
    - `void Greet(string name = "User") { ... } Greet(); // "Hello, User" Greet("Alice"); // "Hello, Alice"`
        
    - Упрощает вызов методов с множеством параметров.
        
          
        
        Пример:
        
        ```
        void SendMessage(string text, string sender = "System", string recipient = "Everyone")
        {
            Console.WriteLine($"Message: '{text}' from {sender} to {recipient}");
        }
        
        SendMessage("Hello!"); // Выведет "Message: 'Hello!' from System to Everyone"
        SendMessage("Hi there!", recipient: "Developers"); // Выведет "Message: 'Hi there!' from System to Developers"
        SendMessage("Greetings", "Admin", "Users");  // Выведет "Message: 'Greetings' from Admin to Users"
        ```
        
        Если не указать значение для необязательного параметра, будет использовано значение по умолчанию.
        
- **Именованные параметры**
    
    - Позволяют передавать аргументы в метод по имени, а не по позиции.
        
    - `void Display(int x, int y) { ... } Display(y: 2, x: 1);`
        
    - Улучшает читаемость кода, особенно при большом количестве параметров.
        
          
        
        Пример:
        
        ```
        void SetCoordinates(int x, int y, int z)
        {
            Console.WriteLine($"X: {x}, Y: {y}, Z: {z}");
        }
        
        SetCoordinates(z: 10, x: 5, y: 8); // Выведет "X: 5, Y: 8, Z: 10"
        ```
        
        Именованные параметры делают код более понятным, особенно когда у метода много параметров одного типа.
        
- **Рекурсия**
    
    - Метод, вызывающий сам себя.
        
    - Переполнение стека: ошибка, когда рекурсия слишком глубокая.
        
    - Стек вызовов: структура данных, хранящая информацию о вызовах методов.
        
    - `int Factorial(int n) { if (n == 0) return 1; else return n * Factorial(n - 1); }`
        
    - Полезно для решения задач, которые можно разбить на более мелкие, похожие подзадачи.
        
          
        
        Пример:
        
        ```
        int Fibonacci(int n)
        {
            if (n <= 1)
                return n;
            else
                return Fibonacci(n - 1) + Fibonacci(n - 2);
        }
        
        Console.WriteLine(Fibonacci(6)); // Выведет 8 (0, 1, 1, 2, 3, 5, 8)
        ```
        
        Рекурсия может быть элегантной, но требует осторожности, чтобы не вызвать переполнение стека.
        
- **Преобразование и приведение типов**
    
    - Явное: требуется указание типа в скобках. `(int)myDouble;`
        
    - Неявное: выполняется автоматически, если преобразование безопасно. `int myInt = 10; double myDouble = myInt;`
        
    - Важно для работы с данными разных типов.
        
          
        
        Пример:
        
        ```
        double pi = 3.14159;
        int approximatePi = (int)pi; // Явное приведение (отбрасывает дробную часть)
        Console.WriteLine(approximatePi); // Выведет 3
        
        int smallNumber = 100;
        long bigNumber = smallNumber; // Неявное преобразование (int в long)
        Console.WriteLine(bigNumber); // Выведет 100
        ```
        
        При явном приведении можно потерять данные, поэтому нужно быть внимательным.
        
- **Арифметическое переполнение**
    
    - checked: вызывает исключение при переполнении.
        
    - unchecked: игнорирует переполнение (значение может быть искажено).
        
    - `checked { int x = int.MaxValue + 1; } // исключение`
        
    - Помогает контролировать поведение при арифметических операциях.
        
          
        
        Пример:
        
        ````
        int maxInt = int.MaxValue;
        try
        {
            checked
            {
                int overflowedInt = maxInt + 1;
                Console.WriteLine(overflowedInt);
            }
        }
        catch (OverflowException ex)
        {
            Console.WriteLine($"Error: {ex.Message}"); // Будет ошибка
        }
        
        unchecked
        {
            int uncheckedInt = maxInt + 1;
            Console.WriteLine(uncheckedInt); // Выведет -2147483648
        }
        ```checked` делает операции безопаснее, но может снизить производительность.  `unchecked` быстрее, но может привести к неожиданным результатам.
        ````
        
- **Nullable**
    
    - Nullable: позволяет присваивать null значимым типам.
        
    - `Nullable<int> nullableInt = null; int? nullableIntShort = null;`
        
    - Важно для работы с данными, которые могут отсутствовать.
        
          
        
        Пример:
        
        ```
        int? age = null;
        if (age.HasValue)
        {
            Console.WriteLine($"Age: {age.Value}");
        }
        else
        {
            Console.WriteLine("Age is not specified.");
        }
        
        int? quantity = 5;
        int? nullableQuantity = quantity;
        Console.WriteLine($"Nullable Quantity: {nullableQuantity}");
        ```
        
        Nullable типы позволяют представить отсутствие значения для значимых типов, что часто встречается при работе с базами данных и другими источниками данных.
        
- **var**
    
    - Не является типом данных.
        
    - Позволяет компилятору выводить тип переменной из присвоенного значения.
        
    - `var message = "Hello"; // message имеет тип string`
        
    - Удобно для сокращения кода, но может снизить читаемость, если тип не очевиден.
        
          
        
        Пример:
        
        ````
        var name = "Alice"; // string
        var count = 10;    // int
        var price = 19.99; // double
        
        Console.WriteLine($"Name: {name}, Count: {count}, Price: {price}");
        ```var` делает код короче, но важно использовать его там, где тип переменной очевиден из присваиваемого значения.
        ````
        
- **enum**
    
    - Набор именованных целочисленных констант.
        
    - Повышает читаемость кода.
        
    
    ```
    enum Days { Sun, Mon, Tue, Wed, Thu, Fri, Sat }
    Days today = Days.Mon;
    
    ```
    
    - Полезно для представления наборов связанных значений.
        
          
        
        Пример:
        
        ````
        enum Status
        {
            Pending,
            Active,
            Completed,
            Failed
        }
        
        Status orderStatus = Status.Active;
        Console.WriteLine($"Order Status: {orderStatus} ({(int)orderStatus})"); // Выведет "Order Status: Active (1)"
        
        Status parsedStatus;
        if (Enum.TryParse("Completed", out parsedStatus))
        {
            Console.WriteLine($"Parsed Status: {parsedStatus}"); // Выведет "Parsed Status: Completed"
        }
        ```enum` позволяет использовать понятные имена вместо числовых кодов, что делает код более читаемым и удобным в поддержке.
        ````
        
- **Класс**
    
    - Шаблон для создания объектов.
        
    - ООП: парадигма программирования, основанная на классах и объектах.
        
    - Объект класса: экземпляр класса.
        
    - Экземпляр класса: конкретное представление класса в памяти.
        
          
        
        Пример:
        
        ```
        class Car
        {
            public string Model;
            public int Year;
        
            public void StartEngine()
            {
                Console.WriteLine($"Engine of {Model} ({Year}) started!");
            }
        }
        
        Car myCar = new Car { Model = "Tesla Model 3", Year = 2023 };
        myCar.StartEngine(); // Выведет "Engine of Tesla Model 3 (2023) started!"
        ```
        
        Классы - это основа ООП, они позволяют создавать собственные типы данных с полями и методами.
        
- **Методы и классы**
    
    - Методы определяют поведение класса.
        
    - Вызов метода объекта класса: `myObject.MyMethod();`
        
          
        
        Пример:
        
        ```
        class Calculator
        {
            public int Add(int a, int b)
            {
                return a + b;
            }
        }
        
        Calculator myCalculator = new Calculator();
        int sum = myCalculator.Add(5, 3);
        Console.WriteLine($"Sum: {sum}"); // Выведет "Sum: 8"
        ```
        
        Методы определяют, что могут делать объекты класса.
        
- **Модификаторы доступа**
    
    - public: доступен везде.
        
    - private: доступен только внутри класса.
        
          
        
        Пример:
        
        ```
        class BankAccount
        {
            public string AccountNumber { get; set; } // Доступен везде
            private decimal balance;             // Доступен только внутри BankAccount
        
            public void Deposit(decimal amount)
            {
                balance += amount;
            }
        
            public decimal GetBalance()
            {
                return balance;
            }
        }
        
        BankAccount account = new BankAccount();
        account.AccountNumber = "12345"; // OK
        // account.balance = 1000;    // Ошибка!  balance - private
        account.Deposit(1000);
        Console.WriteLine($"Balance: {account.GetBalance()}"); // Выведет "Balance: 1000"
        ```
        
        Модификаторы доступа определяют, кто может видеть и изменять члены класса.
        
- **Инкапсуляция**
    
    - Сокрытие данных класса и предоставление доступа к ним через методы.
        
    - Защита данных от неправильного использования.
        
          
        
        Пример:
        
        ```
        class Person
        {
            private int age; // Скрытое поле
        
            public int GetAge()
            {
                return age;
            }
        
            public void SetAge(int value)
            {
                if (value >= 0 && value <= 120)
                {
                    age = value;
                }
                else
                {
                    Console.WriteLine("Invalid age!");
                }
            }
        }
        
        Person person = new Person();
        // person.age = -10; // Ошибка!  age - private
        person.SetAge(30);
        Console.WriteLine($"Age: {person.GetAge()}"); // Выведет "Age: 30"
        person.SetAge(150); // Выведет "Invalid age!"
        ```
        
        Инкапсуляция позволяет контролировать доступ к данным и обеспечивает их целостность.
        
- **Конструктор класса**
    
    - Специальный метод, вызываемый при создании объекта класса.
        
    - Инициализирует поля класса.
        
    - Конструктор по умолчанию: конструктор без параметров, создается компилятором, если не определен другой конструктор.
        
          
        
        Пример:
        
        ```
        class Book
        {
            public string Title;
            public string Author;
        
            public Book(string title, string author) // Конструктор
            {
                Title = title;
                Author = author;
            }
        }
        
        Book myBook = new Book("The Lord of the Rings", "J.R.R. Tolkien");
        Console.WriteLine($"Title: {myBook.Title}, Author: {myBook.Author}");
        ```
        
        Конструкторы позволяют задать начальные значения для полей объекта при его создании.
        
- **Перегрузка конструкторов**
    
    - Определение нескольких конструкторов с разными параметрами.
        
    - Позволяет создавать объекты с разной инициализацией.
        
          
        
        Пример:
        
        ```
        class Rectangle
        {
            public int Width;
            public int Height;
        
            public Rectangle() // Конструктор 1
            {
                Width = 0;
                Height = 0;
            }
        
            public Rectangle(int width, int height) // Конструктор 2
            {
                Width = width;
                Height = height;
            }
        
            public Rectangle(int size) : this(size, size) { } // Конструктор 3, вызывает конструктор 2
        }
        
        Rectangle rect1 = new Rectangle();         // Width = 0, Height = 0
        Rectangle rect2 = new Rectangle(10, 20); // Width = 10, Height = 20
        Rectangle rect3 = new Rectangle(5);    // Width = 5, Height = 5
        ```
        
        Перегрузка конструкторов обеспечивает гибкость при создании объектов.
        
- **Ключевое слово this**
    
    - Ссылка на текущий экземпляр класса.
        
    - Используется для доступа к полям класса и вызова других конструкторов.
        
          
        
        Пример:
        
        ````
        class Employee
        {
            public string Name;
            public int Age;
        
            public Employee(string name) : this(name, 0) // Вызов другого конструктора
            {
            }
        
            public Employee(string name, int age)
            {
                this.Name = name;
                this.Age = age;
            }
        
            public void PrintDetails()
            {
                Console.WriteLine($"Name: {this.Name}, Age: {this.Age}");
            }
        }
        
        Employee emp1 = new Employee("Charlie", 35);
        Employee emp2 = new Employee("David");
        emp1.PrintDetails(); // Выведет "Name: Charlie, Age: 35"
        emp2.PrintDetails(); // Выведет "Name: David, Age: 0"
        ```this` позволяет различать локальные переменные и поля класса, а также вызывать один конструктор из другого.
        ````
        
- **Свойства get set**
    
    - Предоставляют контролируемый доступ к полям класса.
        
    - get: возвращает значение поля.
        
    - set: устанавливает значение поля.
        
    - value: ключевое слово, представляющее присваиваемое значение в set-методе.
        
    - Автоматические свойства: `public int MyProperty { get; set; }` Компилятор создает скрытое поле для хранения значения свойства.
        
          
        
        Пример:
        
        ```
        class Product
        {
            private decimal price;
        
            public decimal Price
            {
                get { return price; }
                set
                {
                    if (value >= 0)
                    {
                        price = value;
                    }
                    else
                    {
                        Console.WriteLine("Price cannot be negative!");
                    }
                }
            }
        
            public string Name { get; set; } // Автоматическое свойство
        }
        
        Product product = new Product();
        product.Price = 10.99m;
        product.Name = "Laptop";
        Console.WriteLine($"Product: {product.Name}, Price: {product.Price}");
        product.Price = -5m; // Выведет "Price cannot be negative!"
        ```
        
        Свойства позволяют инкапсулировать доступ к полям класса, обеспечивая контроль над чтением и записью.
        
- **Статические поля класса**
    
    - Принадлежат не экземпляру класса, а самому классу.
        
    - Общие для всех объектов класса.
        
          
        
        Пример:
        
        ```
        class Counter
        {
            public static int Count; // Статическое поле
        
            public Counter()
            {
                Count++;
            }
        }
        
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        Counter c3 = new Counter();
        Console.WriteLine($"Count: {Counter.Count}"); // Выведет "Count: 3"
        ```
        
        Статические поля хранят значения, общие для всех экземпляров класса.
        
- **Статические методы**
    
    - Принадлежат классу, а не объекту.
        
    - Могут вызываться без создания экземпляра класса.
        
          
        
        Пример:
        
        ```
        class MathHelper
        {
            public static double Square(double x)
            {
                return x * x;
            }
        }
        
        double result = MathHelper.Square(5);
        Console.WriteLine($"Square: {result}"); // Выведет "Square: 25"
        ```
        
        Статические методы предоставляют утилитарные функции, не связанные с конкретным объектом.
        
- **Статический конструктор класса**
    
    - Инициализирует статические поля класса.
        
    - Вызывается один раз при первом обращении к классу.
        
        ```
        class Logger
        {
            public static string LogFilePath;
        
            static Logger()  // Статический конструктор
            {
                LogFilePath = "default.log";
                //  LogFilePath = ConfigurationManager.AppSettings["LogFilePath"]; // Пример чтения из конфигурации
            }
        
            public static void LogMessage(string message)
            {
                 Console.WriteLine($"Logging to {LogFilePath}: {message}");
            }
        }
        
        Logger.LogMessage("Application started.");
        ```
        
        Статические конструкторы используются для инициализации статических членов класса, например, для чтения конфигурации или открытия соединения с базой данных.