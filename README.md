### Соломахин Владислав 
### Урок 67 

Что такое символьная строка?

Символьная строка — это последовательность символов, относящихся к алфавиту определенного языка, которая может включать буквы, цифры, пробелы и специальные знаки. В программировании строки обычно представляются как массивы символов или специальными типами данных.

Почему неудобно заменять строки массивами символов?

Строки, представленные массивами символов, часто имеют фиксированную длину, что затрудняет управление ими (например, при добавлении или удалении символов). Также операции, такие как копирование, конкатенация или поиск подстроки, требуют ручного управления памятью и учета конца строки.

Как объявляются строки в школьном алгоритмическом языке и в Паскале?

В школьном алгоритмическом языке строки могут объявляться как переменные типа Строка, тогда как в Паскале строки могут объявляться с использованием типа String или фиксированного размера, например: Var myString: String[10];.

Как обращаться к элементу строки с заданным номером?

Для обращения к элементу строки по индексу используется синтаксис, например в Паскале: myString[i], где i — индекс (от 1 до длины строки).

Как вычисляется длина строки?

Длина строки вычисляется с использованием стандартной функции, например, в Паскале это функция Length(myString), которая возвращает количество символов в строке.

Что обозначает операция «+» применительно к строкам?

Операция «+» для строк обозначает конкатенацию, то есть объединение двух строк в одну. Например, str1 + str2 вернет строку, состоящую из символов, содержащихся в str1 и str2.

Перечислите основные операции со строками и соответствующие им стандартные функции.

Конкатенация: + или Concat()

Длина: Length()

Поиск подстроки: Pos()

Извлечение подстроки: Copy()

Замена: StringReplace()

Преобразование регистра: UpCase(), LowerCase()

Как определить, что при поиске в строке образец не найден?

При поиске подстроки функция возвращает индекс первого вхождения. Если область поиска истощена и образец не найден, функция возвращает 0 или -1 (в зависимости от языка программирования).

Чем различаются средства школьного алгоритмического языка для работы со строками и Паскаля?

В школьном алгоритмическом языке функции и операции со строками, как правило, более ограничены и менее гибки, в то время как Паскаль предоставляет более широкий набор встроенных функций для работы со строками, позволяющих выполнять сложные операции более эффективно.

Как преобразовать число из символьного вида в числовой и обратно?

Для преобразования символьной строки в число можно использовать функции, такие как StrToInt() в Паскале, а для преобразования числа в строку используется IntToStr().

Почему строку не всегда можно преобразовать в число? Как определить, что преобразование закончилось неудачно?

Преобразование не удается, если строка содержит недопустимые символы (например, буквы). В Паскале можно использовать механизм обработки исключений или функции, которые возвращают статус преобразования.

Объясните выражение «рекурсивный перебор».

Рекурсивный перебор — это метод, при котором функция вызывает сама себя для решения задачи, разбивая её на более простые подзадачи до достижения базового случая.

Сравните на примерах рекурсивные и нерекурсивные методы решения переборных задач.

Пример рекурсивного метода: решение задачи о нахождении всех перестановок строки путем обмена текущего символа с каждым последующим. Нерекурсивный метод может использовать стек для хранения состояний и перебора всех вариантов, избегая самовызовов. Нерекурсивные методы иногда проще для понимания, но рекурсивные могут быть более лаконичными и выразительными.

0

Давайте поочередно реализуем каждую из задач на Python.

Задача 1: Замена букв и регистров
def replace_letters_and_case(s):
    result = []
    for char in s:
        if char == 'а':
            result.append('б')
        elif char == 'б':
            result.append('а')
        elif char.isalpha():
            result.append(char.lower() if char.isupper() else char.upper())
        else:
            result.append(char)
    return ''.join(result)

input_string = input("Введите строку: ")
output_string = replace_letters_and_case(input_string)
print("Результат:", output_string)
Задача 2: Проверка на палиндром
def is_palindrome(s):
    s = ''.join(filter(str.isalnum, s)).lower()  # Убираем неалфавитные символы и переводим в нижний регистр
    return s == s[::-1]

input_string = input("Введите строку: ")
if is_palindrome(input_string):
    print("Строка является палиндромом.")
else:
    print("Строка не является палиндромом.")
Задача 3: Разбор адреса файла на части
def parse_file_path(file_path):
    parts = file_path.split('/')
    for part in parts:
        print(part)

input_file_path = input("Введите адрес файла: ")
parse_file_path(input_file_path)
Задача 4: Вычисление суммы натуральных чисел
def calculate_sum(expression):
    numbers = expression.split('+')
    return sum(int(num) for num in numbers)

input_expression = input("Введите сумму натуральных чисел (например '1+25+3'): ")
result = calculate_sum(input_expression)
print("Результат:", result)
Задача 5: Вывод инициалов и фамилии
def print_initials(full_name):
    parts = full_name.split()
    initials = ''.join(part[0] for part in parts[1:]) + '.'
    last_name = parts[0]
    return f"{initials} {last_name}"

input_full_name = input("Введите фамилию, имя и отчество: ")
result = print_initials(input_full_name)
print("Результат:", result)
Давайте поочередно реализуем предложенные задачи на Python.

Задача 7: Рекурсивная версия процедуры replaceAll
def replace_all_recursive(s, old, new):
    if old not in s:
        return s
    return replace_all_recursive(s.replace(old, new, 1), old, new)

def replace_all_iterative(s, old, new):
    while old in s:
        s = s.replace(old, new)
    return s

# Пример использования
input_string = input("Введите строку: ")
result_recursive = replace_all_recursive(input_string, 'а', 'б')
result_iterative = replace_all_iterative(input_string, 'а', 'б')

print("Рекурсивный результат:", result_recursive)
print("Итеративный результат:", result_iterative)
Сравнение: Рекурсивная версия более элегантна и проста в реализации, но может привести к переполнению стека для больших строк. Итеративная версия более устойчива и предпочтительнее для больших данных.

Задача 8: Изменение расширения файла
def change_extension(filename, new_extension):
    if '.' in filename:
        return '.'.join(filename.split('.')[:-1] + [new_extension])
    else:
        return filename + '.' + new_extension

input_filename = input("Введите имя файла: ")
new_extension = input("Введите новое расширение: ")
result_filename = change_extension(input_filename, new_extension)
print("Новое имя файла:", result_filename)
Задача 9: Подсчет вхождений слова в строку
def count_word_occurrences(s, word):
    return s.split().count(word)

input_string = input("Введите строку: ")
input_word = input("Введите слово для поиска: ")
count = count_word_occurrences(input_string, input_word)
print(f"Слово '{input_word}' встречается {count} раз(а).")
Задача 10: Подсчет футболистов без голов, родившихся с 1998 по 2000
def count_players_no_goals(players):
    count = 0
    for player in players:
        last_name, first_name, birth_year, goals = player.split()
        if 1998 <= int(birth_year) <= 2000 and int(goals) == 0:
            count += 1
    return count

N = int(input("Введите количество футболистов: "))
players_info = [input("Введите информацию о футболисте: ") for _ in range(N)]
result = count_players_no_goals(players_info)
print("Количество футболистов без голов, родившихся с 1998 по 2000:", result)
Задача 11: Футболист с наибольшим количеством голов
def player_with_most_goals(players):
    max_goals = -1
    best_player = ""
    for player in players:
        last_name, first_name, birth_year, goals = player.split()
        if int(goals) > max_goals:
            max_goals = int(goals)
            best_player = f"{last_name} {first_name}"
    return best_player, max_goals

best_player, goals = player_with_most_goals(players_info)
print(f"Футболист с наибольшим количеством голов: {best_player} ({goals} голов)")
Задача 12: Футболисты, забившие хотя бы один гол
def players_with_goals(players):
    return sorted([f"{player.split()[0]} {player.split()[1]}" for player in players if int(player.split()[-1]) > 0])

result_players = players_with_goals(players_info)
print("Футболисты, забившие хотя бы один гол:")
for player in result_players:
    print(player)
Задача 13: Рекурсивный перебор слов заданной длины
def generate_words(length, current_word='', alphabet='абв'):
    if length == 0:
        print(current_word)
        return
    for letter in alphabet:
        generate_words(length - 1, current_word + letter)

K = int(input("Введите длину слова: "))
generate_words(K)
Задача 14: Слова из K букв с буквой «Ы» более 1 раза
def generate_words_with_y(length, current_word=''):
    if length == 0:
        if current_word.count('Ы') > 1:
            print(current_word)
            return 1
        return 0
    count =
















Вот решения для задач, которые вы описали. Я предоставлю примеры кода на Python для каждой задачи.

### Задача 1: Нахождение минимальных и максимальных элементов матрицы и их индексов

```python
import numpy as np

# Генерация случайной матрицы
matrix = np.random.randint(0, 100, (5, 5))
print("Матрица:")
print(matrix)

min_value = np.min(matrix)
max_value = np.max(matrix)
min_index = np.argwhere(matrix == min_value)[0]
max_index = np.argwhere(matrix == max_value)[0]

print(f"Минимальный элемент: {min_value}, Индекс: {min_index}")
print(f"Максимальный элемент: {max_value}, Индекс: {max_index}")
Задача 2: Нахождение минимальных и максимальных элементов с четными индексами
import numpy as np

matrix = np.random.randint(0, 100, (5, 5))
print("Матрица:")
print(matrix)

even_elements = []
for i in range(matrix.shape[0]):
    for j in range(matrix.shape[1]):
        if i % 2 == 0 and j % 2 == 0:
            even_elements.append(matrix[i][j])

if even_elements:
    min_even = min(even_elements)
    max_even = max(even_elements)
    print(f"Минимальный элемент с четными индексами: {min_even}")
    print(f"Максимальный элемент с четными индексами: {max_even}")
else:
    print("Нет элементов с четными индексами.")
Задача 3: Вывод строки матрицы
import numpy as np

matrix = np.random.randint(0, 100, (5, 5))
print("Матрица:")
print(matrix)

row_index = 2  # Измените на нужный индекс
print(f"Строка с индексом {row_index}: {matrix[row_index]}")
Задача 4: Вывод столбца матрицы
import numpy as np

matrix = np.random.randint(0, 100, (5, 5))
print("Матрица:")
print(matrix)

col_index = 1  # Измените на нужный индекс
print(f"Столбец с индексом {col_index}: {matrix[:, col_index]}")
Задача 5: Заполнение матрицы случайными числами выше главной диагонали
import numpy as np

size = 5
matrix = np.zeros((size, size), dtype=int)
for i in range(size):
    for j in range(size):
        if j > i:
            matrix[i][j] = np.random.randint(1, 100)

print("Матрица с заполненными элементами выше главной диагонали:")
print(matrix)
Задача 6: Заполнение матрицы случайными числами, нули выше побочной диагонали
import numpy as np

size = 5
matrix = np.random.randint(0, 100, (size, size))
print("Исходная матрица:")
print(matrix)

for i in range(size):
    for j in range(size):
        if j < size - 1 - i:
            matrix[i][j] = 0

print("Матрица с нулями выше побочной диагонали:")
print(matrix)
Задача 7: Заполнение матрицы 7x7 случайными числами
import numpy as np

matrix = np.random.randint(0, 100, (7, 7))
print("Матрица 7x7:")
print(matrix)
Задача 8: Заполнение матрицы по спирали и змейкой
def spiral_fill(n, m):
    matrix = [[0]*m for _ in range(n)]
    num = 1
    left, right, top, bottom = 0, m-1, 0, n-1

    while left <= right and top <= bottom:
        for i in range(left, right + 1):
            matrix[top][i] = num
            num += 1
        top += 1

        for i in range(top, bottom + 1):
            matrix[i][right] = num
            num += 1
        right -= 1

        if top <= bottom:
            for i in range(right, left - 1, -1):
                matrix[bottom][i] = num
                num += 1
            bottom -=



Вот решения для задач, которые вы описали. Я предоставлю примеры кода на Python для каждой задачи.

### Задача 9: Транспонирование квадратной матрицы

```python
import numpy as np

# Генерация случайной квадратной матрицы размером 4x4
size = 4
matrix = np.random.randint(0, 100, (size, size))
print("Исходная матрица:")
print(matrix)

# Транспонирование матрицы
transposed_matrix = matrix.T
print("Транспонированная матрица:")
print(transposed_matrix)
Задача 10: Преобразование изображения в черно-белый
import numpy as np

# Генерация случайной матрицы, представляющей изображение
rows, cols = 5, 5
image = np.random.randint(0, 256, (rows, cols))
print("Исходное изображение:")
print(image)

# Вычисление средней яркости
average_brightness = np.mean(image)
print(f"Средняя яркость: {average_brightness}")

# Преобразование изображения в черно-белый
bw_image = np.where(image < average_brightness, 0, 255)
print("Черно-белое изображение:")
print(bw_image)
Задача 11: Отражение изображения сверху вниз
import numpy as np

# Генерация случайной матрицы, представляющей изображение
image = np.random.randint(0, 256, (5, 5))
print("Исходное изображение:")
print(image)

# Отражение изображения сверху вниз
reflected_image = np.flipud(image)
print("Отраженное изображение:")
print(reflected_image)
Задача 12: Поворот изображения вправо на 90 градусов
import numpy as np

# Генерация случайной матрицы, представляющей изображение
image = np.random.randint(0, 256, (3, 3))
print("Исходное изображение:")
print(image)

# Поворот изображения вправо на 90 градусов
rotated_image = np.rot90(image, k=-1)  # k=-1 поворот вправо
print("Изображение после поворота вправо на 90 градусов:")
print(rotated_image)
Задача 13: Игра в крестики-нолики
def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 9)

def check_winner(board):
    # Проверка строк
    for row in board:
        if row[0] == row[1] == row[2] != " ":
            return row[0]
    # Проверка столбцов
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] != " ":
            return board[0][col]
    # Проверка диагоналей
    if board[0][0] == board[1][1] == board[2][2] != " ":
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] != " ":
        return board[0][2]
    return None

def tic_tac_toe():
    board = [[" " for _ in range(3)] for _ in range(3)]
    current_player = "X"
    for _ in range(9):
        print_board(board)
        row = int(input(f"Игрок {current_player}, выберите строку (0-2): "))
        col = int(input(f"Игрок {current_player}, выберите столбец (0-2): "))
        
        if board[row][col] == " ":
            board[row][col] = current_player
            winner = check_winner(board)
            if winner:
                print_board(board)
                print(f"Игрок {winner} выиграл!")
                return
            current_player = "O" if current_player == "X" else "X"
        else:
            print("Эта ячейка уже занята. Попробуйте снова.")
    print_board(board)
    print("Ничья!")

tic_tac_toe()
Задача 14: Подсчет островов на карте
import numpy as np

def count_islands(map_matrix):
    rows, cols = map_matrix.shape
    visited = np.zeros((rows, cols), dtype=bool)

    def dfs(r,


### !Урок 68-69!


Различия текстовых и двоичных файлов: Текстовые файлы содержат данные в виде символов, которые могут быть прочитаны и интерпретированы человеком (например, ASCII или UTF-8). Двоичные файлы, в свою очередь, содержат данные в формате, который не предназначен для непосредственного чтения человеком (например, изображения, аудио, исполняемые файлы). Можно сказать, что текстовый файл — это частный случай двоичного файла, так как текстовые файлы также представляют собой последовательность байтов, но с определенной интерпретацией.

Принцип сэндвича: Этот принцип подразумевает, что при работе с файлами данные могут быть записаны или прочитаны в определенном порядке, где "начинка" (данные) находится между "хлебом" (метаинформация, заголовки и т. д.). Например, при записи данных в файл сначала может быть записан заголовок, затем сами данные, а затем завершающая информация.

Блокировка открытых файлов: Когда файл открыт одной программой, он блокируется для других программ, чтобы избежать конфликтов при одновременном доступе к данным. Это предотвращает возможные ошибки, такие как запись данных в файл, который уже открыт для чтения другой программой.

Рекомендация закрывать файлы вручную: Закрытие файлов вручную позволяет гарантировать, что все данные были правильно записаны и освобождаются ресурсы, связанные с файлом. В ситуациях, когда программа неожиданно завершается (например, из-за ошибки), не закрытые файлы могут привести к потере данных или повреждению файловой системы.

Файловая переменная: Файловая переменная — это переменная, которая хранит информацию о состоянии открытого файла (например, указатель на текущую позицию в файле, режим доступа и т. д.). Использование файловой переменной вместо имени файла позволяет программе управлять несколькими открытыми файлами одновременно и отслеживать их состояние.

Использование одной файловой переменной для нескольких файлов: Одна и та же файловая переменная может быть использована для работы с несколькими файлами, если файл был закрыт и затем открыт снова с использованием той же переменной. Однако, если переменная все еще ссылается на открытый файл, то ее нельзя использовать для работы с другим файлом.

Последовательный доступ к данным: Последовательный доступ к данным подразумевает, что данные читаются или записываются в файле последовательно, от начала к концу, без возможности произвольного доступа к произвольным частям файла.

Чтение данных из файла с его начала: Чтобы начать чтение данных из файла с его начала, необходимо установить указатель на начало файла. В большинстве языков программирования для этого используется функция, например, seek(0) или аналогичная.

Определение конца данных в файле: Конец данных в файле можно определить, проверяя, возвращает ли функция чтения (например, read()) значение, указывающее на конец файла (EOF). Также может использоваться проверка на ошибку или специальный символ, указывающий на конец данных.

Максимальное количество данных в файле: Знать максимальное количество данных в файле важно в ситуациях, когда необходимо выделить фиксированное количество памяти для хранения данных. В других случаях, например, при чтении текстовых файлов построчно, это не требуется, так как данные могут быть обработаны по мере их поступления.

Открытие нескольких файлов одновременно: Открытие нескольких файлов одновременно может быть необходимо в ситуациях, когда программа должна сравнивать данные из разных файлов, объединять их, выполнять операции чтения и записи в разные файлы одновременно или обрабатывать данные из нескольких источников.

Среднее арифметическое чисел в файле def calculate_average(input_file, output_file): try: with open(input_file, 'r') as f: numbers = [float(line.strip()) for line in f if line.strip()]

 average = sum(numbers) / len(numbers) if numbers else 0
 
 with open(output_file, 'w') as f:
     f.write(f'Среднее арифметическое: {average}\n')
except Exception as e: print(f'Ошибка: {e}')

calculate_average('input.txt', 'average_output.txt') 2. Минимальное и максимальное четных положительных чисел def min_max_even(input_file, output_file): try: with open(input_file, 'r') as f: even_numbers = [int(line.strip()) for line in f if line.strip() and int(line.strip()) > 0 and int(line.strip()) % 2 == 0]

    if even_numbers:
        min_even = min(even_numbers)
        max_even = max(even_numbers)
        result = f'Минимальное: {min_even}, Максимальное: {max_even}\n'
    else:
        result = 'Четные положительные числа не найдены.\n'
    
    with open(output_file, 'w') as f:
        f.write(result)
except Exception as e:
    print(f'Ошибка: {e}')
min_max_even('input.txt', 'min_max_output.txt') 3. Длина цепочки целых чисел def count_integers(input_file, output_file): try: with open(input_file, 'r') as f: numbers = [line.strip() for line in f if line.strip()]

    count = len(numbers)
    
    with open(output_file, 'w') as f:
        f.write(f'Количество целых чисел: {count}\n')
except Exception as e:
    print(f'Ошибка: {e}')
count_integers('input.txt', 'count_output.txt') 4. Сортировка по последней цифре def sort_by_last_digit(input_file, output_file): try: with open(input_file, 'r') as f: numbers = [int(line.strip()) for line in f if line.strip()]

    sorted_numbers = sorted(numbers, key=lambda x: x % 10)
    
    with open(output_file, 'w') as f:
        for number in sorted_numbers:
            f.write(f'{number}\n')
except Exception as e:
    print(f'Ошибка: {e}')
sort_by_last_digit('input.txt', 'sorted_by_last_digit.txt') 5. Сортировка по сумме цифр def sum_of_digits(n): return sum(int(digit) for digit in str(abs(n)))

def sort_by_digit_sum(input_file, output_file): try: with open(input_file, 'r') as f: numbers = [int(line.strip()) for line in f if line.strip()]

    sorted_numbers = sorted(numbers, key=sum_of_digits)
    
    with open(output_file, 'w') as f:
        for number in sorted_numbers:
            f.write(f'{number}\n')
except Exception as e:
    print(f'Ошибка: {e}')
sort_by_digit_sum('input.txt', 'sorted_by_digit_sum.txt') 6. Объединение и сортировка двух массивов def merge_sorted_files(file1, file2, output_file): try: with open(file1, 'r') as f1, open(file2, 'r') as f2: numbers1 = [int(line.strip()) for line in f1 if line.strip()] numbers2 = [int(line.strip()) for line in f2 if line.strip()]

    merged_numbers = sorted(numbers1 + numbers2)
    
    with open(output_file, 'w') as f:
        for number in merged_numbers:
            f.write(f'{number}\n')
except Exception as e:
    print(f'Ошибка: {e}')
merge_sorted_files('file1.txt', 'file2.txt', 'merged_output.txt') 7. Обработка ошибок в программе (пример с собаками) class Dog: def init(self, name, age): try: self.name = name self.age = int(age) except ValueError: print("Ошибка: возраст должен быть числом.") self.age = None

def main(): try: dogs = [] with open('dogs.txt', 'r') as f: for line in f: name, age = line.strip().split(',') dogs.append(Dog(name, age)) except Exception as e: print(f'Ошибка: {e}')

main() 8. Удаление слов-паразитов def remove_fillers(input_file, output_file): try: with open(input_file, 'r') as f: text = f.read()

    filtered_text = ' '.join(word for word in text.split() if word != 'короче')
    
    with open(output_file, 'w') as f:
        f.write(filtered_text)
except Exception as e:
    print(f'Ошибка: {e}')
remove_fillers('input.txt', 'filtered_output.txt') 9. Подсчет количества слов в тексте def count_words(input_file, output_file): try: with open(input_file, 'r') as f: text = f.read()

    word_count = len(text.split())
    
    with open(output_file, 'w') as f:
        f.write(f'Количество слов: {word_count}\n')
except Exception as e:
    print(f'Ошибка: {e}')
count_words('input.txt', 'word_count_output.txt') 10. Строки с словами, начинающимися на «А» def lines_with_a(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    filtered_lines = [line for line in lines if any(word.startswith('А') for word in line.split())]
    
    with open(output_file, 'w') as f:
        f.writelines(filtered_lines)
except Exception as e:
    print(f'Ошибка: {e}')
lines_with_a('input.txt', 'lines_with_a_output.txt') Эти программы обрабатывают различные задачи по работе с файлами и данными, как вы и запросили. Не забудьте заменить имена файлов на актуальные для вашего проекта.

Слова, начинающиеся с буквы «А» def words_starting_with_a(input_file, output_file): try: with open(input_file, 'r') as f: text = f.read()

words = [word for word in text.split() if word.startswith('А') or word.startswith('а')]

with open(output_file, 'w') as f:
    for word in words:
        f.write(f'{word}\n')
except Exception as e: print(f'Ошибка: {e}')

words_starting_with_a('input.txt', 'words_with_a_output.txt') 12. Замена слова «паровоз» на «пароход» def replace_word(input_file, output_file, old_word, new_word): try: with open(input_file, 'r') as f: text = f.read()

    modified_text = text.replace(old_word, new_word)
    
    with open(output_file, 'w') as f:
        f.write(modified_text)
except Exception as e:
    print(f'Ошибка: {e}')
replace_word('input.txt', 'modified_output.txt', 'паровоз', 'пароход') 13. Фамилии и имена учеников с баллами больше 80 def students_above_80(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    students = [line.strip() for line in lines if line.strip() and int(line.split()[-1]) > 80]
    
    with open(output_file, 'w') as f:
        for student in students:
            f.write(f'{student}\n')
except Exception as e:
    print(f'Ошибка: {e}')
students_above_80('exam_results.txt', 'students_above_80.txt') 14. Нумерация студентов с баллами больше 80 def numbered_students_above_80(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    students = [line.strip() for line in lines if line.strip() and int(line.split()[-1]) > 80]
    
    with open(output_file, 'w') as f:
        for index, student in enumerate(students, start=1):
            f.write(f'{index}) {student}\n')
except Exception as e:
    print(f'Ошибка: {e}')
numbered_students_above_80('exam_results.txt', 'numbered_students_above_80.txt') 15. Сокращение имени до одной буквы def abbreviated_students_above_80(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    students = [line.strip() for line in lines if line.strip() and int(line.split()[-1]) > 80]
    
    abbreviated = [f'{student.split()[1][0]}. {student.split()[0]}' for student in students]
    
    with open(output_file, 'w') as f:
        for index, student in enumerate(abbreviated, start=1):
            f.write(f'{index}) {student}\n')
except Exception as e:
    print(f'Ошибка: {e}')
abbreviated_students_above_80('exam_results.txt', 'abbreviated_students_above_80.txt') 16. Сортировка по алфавиту (по фамилии) def alphabetically_sorted_students(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    students = [line.strip() for line in lines if line.strip() and int(line.split()[-1]) > 80]
    
    abbreviated = [f'{student.split()[1][0]}. {student.split()[0]}' for student in students]
    sorted_students = sorted(abbreviated, key=lambda x: x.split()[1])  # Сортировка по фамилии
    
    with open(output_file, 'w') as f:
        for index, student in enumerate(sorted_students, start=1):
            f.write(f'{index}) {student}\n')
except Exception as e:
    print(f'Ошибка: {e}')
alphabetically_sorted_students('exam_results.txt', 'sorted_students_above_80.txt') 17. Сортировка по убыванию полученного балла def sorted_by_score_descending(input_file, output_file): try: with open(input_file, 'r') as f: lines = f.readlines()

    students = [line.strip().split() for line in lines if line.strip()]
    students_with_scores = [(student[0], student[1], int(student[2])) for student in students]

    # Фильтруем студентов с баллами больше 80
    filtered_students = [student for student in students_with_scores if student[2] > 80]
    
    # Сортировка по убыванию баллов
    sorted_students = sorted(filtered_students, key=lambda x: x[2], reverse=True)
    
    with open(output_file, 'w') as f:
        for index, (surname, name, score) in enumerate(sorted_students, start=1):
            f.write(f'{index}) {surname} {name} {score}\n')
except Exception as e:
    print(f'Ошибка: {e}')
sorted_by_score_descending('exam_results.txt', 'sorted_students_by_score.txt') Эти программы выполняют ваши задачи, обрабатывая текстовые файлы и выводя результаты в соответствии с вашими требованиями. Не забудьте заменить имена файлов на актуальные для вашего проекта.

69

Как вы понимаете высказывание К. Ф. Гаусса? К. Ф. Гаусс, известный математик, сделал много вкладов в различные области математики и науки. Одним из его известных высказываний является: "Всякая ошибка, если она не будет исправлена, становится правдой". Это подчеркивает важность точности и внимательности в измерениях и вычислениях, а также необходимость проверки и коррекции ошибок.

Какие величины можно измерять? Какие приборы для этого используются? Приведите примеры. Величины, которые можно измерять, включают:

Длину (например, линейка, рулетка) Массу (например, весы) Температуру (например, термометр) Давление (например, манометр) Электрический ток (например, амперметр) Напряжение (например, вольтметр) Какова цена деления у ваших наручных часов? Цена деления у наручных часов обычно составляет 1 секунду, что означает, что стрелка секундомера перемещается на одно деление каждую секунду.

Как определить цену деления для приборов с цифровыми индикаторами? Приведите примеры. Цена деления для цифровых приборов определяется как разница между двумя соседними значениями на дисплее. Например, если цифровой термометр показывает 20,0 °C и 20,1 °C, то цена деления составляет 0,1 °C. Если вольтметр показывает 1,20 В и 1,21 В, то цена деления составляет 0,01 В.

Что такое абсолютная и относительная погрешности? Какое из этих значений более важно в практических задачах?

Абсолютная погрешность — это разница между измеренным значением и истинным значением, выраженная в тех же единицах измерения. Например, если истинное значение 5 см, а измеренное 4,8 см, то абсолютная погрешность составляет 0,2 см. Относительная погрешность — это отношение абсолютной погрешности к истинному значению, часто выраженное в процентах. В приведенном примере относительная погрешность будет (0,2 см / 5 см) * 100% = 4%. В практических задачах более важно учитывать относительную погрешность, так как она показывает, насколько значима ошибка относительно размера измеряемой величины. Что такое вычислительно неустойчивый метод? Вычислительно неустойчивый метод — это метод, при использовании которого небольшие ошибки в исходных данных могут привести к значительным ошибкам в результатах. Это может происходить, например, при вычислении корней полиномов или при решении систем линейных уравнений, если матрица плохо обусловлена.

Перечислите источники погрешностей при компьютерных вычислениях.

Ошибки округления Ошибки измерения Неустойчивые алгоритмы Ограниченная точность представления чисел (например, использование чисел с плавающей запятой) Человеческий фактор (ошибки ввода данных) Какие задачи изучает вычислительная математика? Вычислительная математика изучает задачи, связанные с численным решением математических проблем, включая:

Численное интегрирование и дифференцирование Решение систем линейных и нелинейных уравнений Оптимизация Моделирование физических процессов Анализ устойчивости численных методов Сообщения а) «Абсолютная и относительная погрешность» Абсолютная погрешность — это разница между измеренным значением и истинным значением. Она выражается в тех же единицах измерения, что и само значение. Относительная погрешность — это отношение абсолютной погрешности к истинному значению, выраженное в процентах. Относительная погрешность позволяет оценить значимость ошибки относительно размера измеряемой величины и часто важнее абсолютной, так как показывает, насколько ошибка влияет на результат.

б) «Вычислительная устойчивость методов» Вычислительная устойчивость методов — это свойство численных алгоритмов, при котором небольшие изменения в входных данных приводят к небольшим изменениям в выходных данных. Устойчивые методы позволяют получать надежные результаты, даже если данные имеют определенные погрешности. Примеры устойчивых методов включают методы интерполяции, численного интегрирования и решения линейных уравнений.

Задачи Как изменятся абсолютная и относительная погрешности результата, если при вычислении площади сечения использовать число 3,147? Если вместо числа π (приблизительно 3,14159) использовать число 3,147, то абсолютная погрешность будет равна разнице между истинным значением площади и рассчитанным значением. Относительная погрешность будет определяться как отношение абсолютной погрешности к истинному значению площади. Это зависит от конкретного случая и размеров сечения.

Радиус шарика R измерили с точностью 0,1 см и получили 1,2 см. Затем рассчитали его объём по формуле V
4 3 π R 3 V= 3 4

πR 3 . Запишите ответ в этой задаче, оставив нужное количество значащих цифр. Сначала вычислим объём:

V
4 3 π ( 1 , 2 ) 3 ≈ 4 3 ⋅ 3 , 14159 ⋅ 1 , 728 ≈ 7 , 23822947387088 см 3 V= 3 4

π(1,2) 3 ≈ 3 4

⋅3,14159⋅1,728≈7,23822947387088 см 3

С учётом точности измерения радиуса (0,1 см) и округления, ответ можно записать как:

V ≈ 7 , 24 см 3 V≈7,24 см 3

С помощью рулетки размеры бруса (220 см х 11 см х 10 см) измерили с точностью 1 см. Определите его объём. Запишите ответ с учётом точности полученного результата. Объём бруса рассчитывается по формуле:

V
220 см × 11 см × 10 см
24200 см 3 V=220 см×11 см×10 см=24200 см 3

С учётом погрешности измерений (1 см), объём можно записать как:

V
24200 ± 220 см 3 V=24200±220 см 3

Пётр и Павел измеряют плотность меди. У них есть медные бруски разной величины, линейка и весы. Пётр взял брусок с размерами (по результатам измерений) 2 х 2 х 2 см, а Павел - с размерами 5 х 5 х 5 см. При измерении массы брусков у Петра получилось 70 г, а у Павла 1120 г. Погрешность измерения длины — 1 мм, погрешность измерения массы 10 г. С какой абсолютной и относительной погрешностью определили плотность меди Пётр и Павел? Какой брусок нужно было выбирать, чтобы погрешность была наименьшей?

Пётр:

Объём: V
2 × 2 × 2
8 см 3 V=2×2×2=8 см 3

Масса: m
70 г m=70 г Плотность: ρ
m V
70 8
8 , 75 г/см 3 ρ= V m

= 8 70

=8,75 г/см 3

Погрешности:

Абсолютная погрешность объёма: Δ V
3 × 1 см
3 см 3 ΔV=3×1 см=3 см 3

Абсолютная погрешность массы: Δ m
10 г Δm=10 г Плотность с погрешностью:

Δ ρ
ρ × ( Δ m m ) 2 + ( Δ V V ) 2 Δρ=ρ× ( m Δm

) 2 +( V ΔV

) 2

Δ ρ
8 , 75 × ( 10 70 ) 2 + ( 3 8 ) 2 ≈ 8 , 75 × 0 , 0204 + 0 , 1406 ≈ 8 , 75 × 0 , 387 ≈ 3 , 39 г/см 3 Δρ=8,75× ( 70 10

) 2 +( 8 3

) 2

≈8,75× 0,0204+0,1406

≈8,75×0,387≈3,39 г/см 3

Павел:

Объём: V
5 × 5 × 5
125 см 3 V=5×5×5=125 см 3

Масса: m
1120 г m=1120 г Плотность: ρ
m V
1120 125
8 , 96 г/см 3 ρ= V m

= 125 1120

=8,96 г/см 3

Погрешности:

Абсолютная погрешность объёма: Δ V
3 × 1 см
3 см 3 ΔV=3×1 см=3 см 3

Абсолютная погрешность массы: Δ m
10 г Δm=10 г Плотность с погрешностью:

Δ ρ
8 , 96 × ( 10 1120 ) 2 + ( 3 125 ) 2 ≈ 8 , 96 × 0 , 00079 + 0 , 0576 ≈ 8 , 96 × 0 , 240 ≈ 2 , 15 г/см 3 Δρ=8,96× ( 1120 10

) 2 +( 125 3

) 2

≈8,96× 0,00079+0,0576

≈8,96×0,240≈2,15 г/см 3

Вывод: Плотность Петра: 8 , 75 ± 3 , 39 г/см 3 8,75±3,39 г/см 3

Плотность Павла: 8 , 96 ± 2 , 15 г/см 3 8,96±2,15 г/см 3

Таким образом, брусок Павла имеет меньшую относительную погрешность, и его результаты более точны


