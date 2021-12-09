## Fusion - Blockchain Application Platform

Main Components:-
1. Fusion Language, Functional Programming Language.
2. Reactor, Virtual Stack Machine.
3. Plasma, Fusion Language to Reactor Code Compiler.
4. Helium, Code Manager.

### Fusion Language

Types :-
1. Integer -> 10
2. Floating Point -> 10.0
3. Boolean -> true/false
4. String -> "string"
5. List -> [ 1,2,3 ]
6. Tuple -> ("number", 10)
7. Record -> { "key_1": 1, "key_2": 2 }

Assignments :-
1. let -> let a = 10;
2. const -> let A = 10;

Operators :-
1. Equal (=)
2. And (&)
3. Or (||)

Control Flow :-
1. Conditional
    - If
    - Case
2. Loop
    - While
    - For

Standard Library (std) :-
1. Mathematics (math)
    - From String -> from_str(string, radix)
    - Into String -> into_str(number, radix)
    - Addition -> add(a, b)
    - Subtraction -> sub(a, b)
    - Multiplication -> mul(a, b)
    - Division -> div(a, b)
    - Remainder -> rem(a, b)
    - Modulo -> mod(a, b)
    - Exponentiation -> pow(a, e)

2. String (string) :-
    - Bytes -> bytes(string)
    - Hexadecimal -> hex(string)
    - Lowercase -> lower(string)
    - Merge -> merge(string, string)
    - Replace -> replace(string, old string, new string)
    - Uppercase -> upper(string)

3. List (list) :-
    - Any -> any(list, condition)
    - Dedup -> dedup(list)
    - Delete -> del(list, value)
    - Each -> each(list, assign, lambda)
    - Filter -> filter(list, assign, condition)
    - Get -> get(list, index)
    - Length -> len(list)
    - Map -> map(list, assign, lambda)
    - Merge -> merge(list, list)
    - Pop -> pop(list, index)
    - Put -> put(list, value)
    - Reverse -> reverse(list)
    - Slice -> slice(list, start index, stop index)

4. Record (record) :-
    - Delete -> del(record, key)
    - Get -> get(record, key)
    - Merge -> merge(record, record)
    - Pop -> pop(record, key)
    - Put -> put(record, key value pair)

5. Accounts (account) :-
    - Create -> create(0xFFFF)
    - Balance -> balance(0xFFFF)
    - Storage (storage)
        - Put -> put(0xFFFF, "key", "value")
        - Get -> get(0xFFFF, "key")
        - Delete -> delete(0xFFFF, "key")

### Reactor - Virtual Stack Machine

Op Codes :-
1. General
    - Stop
2. Memory
    - Put
    - Get
3. Account
    - Create
    - Balance
    - Storage Put
    - Storage Get
    - Storage Delete
4. Arithmetic
    - Addition
    - Subtraction
    - Multiplication
    - Division
    - Remainder
    - Modulo
    - Exponentiation
    - Modular Inverse
5. Comparison
    - Less Than
    - Greater Than
    - Equal To
6. Bitwise
    - Not
    - And
    - Or
    - Xor
    