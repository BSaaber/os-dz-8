# Мовшин Максим | БПИ213 | ДЗ-8
компиляция:
```
gcc common.c writer.c -o writer -lpthread -lrt && gcc common.c reader.c -o reader -lpthread -lrt
```

Ввод - Терминал 1:
```
./writer
```
Ввод - Терминал 2:
```
./reader
```
Пример вывода - writer:
```
Object is open: name = /posix-shar-object, id = 0x3
Memory size set and = 52
mmap checkout
checking: writer_number = 1
Writer 57580: I am first for this work! :)
Producer 57580 writes value = 6 to cell [2]
Producer 57580 writes value = 0 to cell [3]
Producer 57580 writes value = 6 to cell [4]
Producer 57580 writes value = 4 to cell [5]
Producer 57580 writes value = 4 to cell [6]
Producer 57580 writes value = 2 to cell [7]
Producer 57580 writes value = 2 to cell [8]
Producer 57580 writes value = 6 to cell [9]
Producer 57580 writes value = 10 to cell [2]
Producer 57580 writes value = 9 to cell [3]
Producer 57580 writes value = 8 to cell [4]
Writer(SIGTERM) <--- Reader(SIGINT)
Writer: bye!!!
```
Пример вывода - reader:
```
Consumer 57593 started
Memory object is opened: name = /posix-shar-object, id = 0x3
Memory size set and = 52
Consumer 57593: Reads value = 6 from cell [3], factorial = 720
Consumer 57593: Reads value = 0 from cell [4], factorial = 1
Consumer 57593: Reads value = 6 from cell [5], factorial = 720
Consumer 57593: Reads value = 4 from cell [6], factorial = 24
Consumer 57593: Reads value = 4 from cell [7], factorial = 24
Consumer 57593: Reads value = 2 from cell [8], factorial = 2
Consumer 57593: Reads value = 2 from cell [9], factorial = 2
Consumer 57593: Reads value = 6 from cell [2], factorial = 720
Consumer 57593: Reads value = 10 from cell [3], factorial = 3628800
Consumer 57593: Reads value = 9 from cell [4], factorial = 362880
^CReader(SIGINT) ---> Writer(SIGTERM)
Reader: bye!!!
```
