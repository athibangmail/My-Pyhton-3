## FrozenSet
------------
### FrozenSet are the set is iterable and immutable
- Create FrozenSet:
    - simple frozenset:
    ````
    >> num = (1,2,3,4,5,6,7,8,9)
    >> my_set = frozenset(num)
    >> my_set
    frozenset({1,2,3,4,5,6,7,8,9})
    ````

- frozenset create with dictionary 
    - dictionary input of frozenset
    ````
    >> my_dict = {"name" : "Athiban","age": 27}
    >> key = frozenset(my_dict)
    >> key
    frozenset({'name', 'age'})
    ````
- frozenset are immutable so can't change
    - ````
        >> my_list = [1,2,4,5,56]
        >> my_set = frozenset(my_list)
        >> my_set[0] = 33
        Traceback (most recent call last):
        File "/home/0fbd773df8aa631590ed0f3f865c1437.py", line 12, in 
            my_set[0] = 33
        TypeError: 'frozenset' object does not support item assignment

    ````
