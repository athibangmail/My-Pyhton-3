# Sets 
#### Sets is a collections of data types it can contains only immutable objects and will not be appeared second time basically it wont allow duplicates 
- create Sets:
    - below the example:  
        ```` 
        >> my_set = set({"New York","Mauritius", "Tokyo", "Delhi", })
        >> my_set
        {'Delhi', 'New York', 'Mauritius', 'Tokyo'} 
        ````      
        
    - sets are maintain un ordered elements, it will not keep the same order how you are adding

- Duplicates elements:
    - Adding czechoslovakia double the time. 
        ````
        >> my_set = ({"czechoslovakia", "czechoslovakia})
        >> my_set
        {'czechoslovakia'}
        ````

- you can't make the set from mutable object but sets is **Mutable**
    - trying to add list in the set functions
        ````
        >> my_set = set({["China", "United States of America", "Belgium"], ["Beijing", "New York", "Brussels"]})
        Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
        TypeError: unhashable type: 'list'
        ````
    - adding new item in two the list
        ````
        >> my_set = set({"Australia", "Japan", "colombia"})
        >> my_set.add("fiji")
        >> my_set
        {'colombia', 'Australia', 'Japan', 'fiji'}
        ````
        - added fiji in the my_set so it is mutable

- *FrozenSet* is the set for immutable, can't be changed once declared.
    - adding item in frozen set
        ````
        >> my_set = frozenset({"Asia Fusion", "Mexican", "American", "South India"})
        >> my_set.add("North India")
        Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
        AttributeError: 'frozenset' object has no attribute 'add'
        ````
    - trowed a error because of it is immutable

- *Union* of sets 
    -  union will join of one set from other set
        ````
        >> olympics_sports_set = set({"Archery", "Athletics", "Mountain Bike"})  
        >> paralympics_sports_set = set({"Archery", "Athletics", "Mountain Bike"})
        >> all_sports_set = olympics_sports_set.union(paralympics_sports_set)
        >> all_sports_set
        {'Mountain Bike', 'Athletics', 'Archery'}
        ````
    - the above example combine olympics games and paralympics games
        ````
        >> all_sports_set = olympics_sports_set | paralympics_sports_set
        >> all_sports_set
        {'Mountain Bike', 'Athletics', 'Archery'}
        ````
- *Intersection* of sets 
    - Intersection will take only common elements of both the sets
    ```
    >> indian_actors = set({"Rajini Kanth", "Dhanush", "Amitabh Pachchan"})
    >> hollywood_actors = set({"Leaonardo Dicaprio", "Sylvester Stallone", "Dhanush"})
    >> hollywood_actors.Intersection(indian_actors)
    {'Dhansh'}
    ````
    - The common actor from both the list is *Dhanush*
    ````
    >> hollywood_actors & indian_actors
    {'Dhansh'}
    ````

- *Difference* of Sets
    - Difference for between two sets
        ````
        >> hollywood_actors.difference(indian_actors)
        {'Sylvester Stallone', 'Leaonardo Dicaprio'}
        ````
    - there is a one more way to do this
        ````
        >> hollywood_actors - indian_actors
        {'Sylvester Stallone', 'Leaonardo Dicaprio'}
        ````

- *isSubset* of sets
    - isSubset function will give true if that set is a subset of the other set
        ```
        >> hollywood_actors_set = set({"Tom Cruise", "Will Smith", "Johnny Depp", "Arnold"})
        >> titanic_actors = set({"Kate Winslet" "Leaonardo Dicaprio"})
        >> titanic_actors.issubset(hollywood_actors_set)
        False
        ````
        - it will be `True` if the titanic sets actors is present in the hollywood actors sets
        - another way to do it
        ````
        >> titanic_actors > hollywood_actors
        False
        >> titanic_actors >= hollywood_actors
        False
        >> titanic_actors > titanic_actors
        False
        >> titanic_actors >= titanic_actors
        True
        ````
- *isSuperSet* of sets
    - isSuperSet functions is the opposite of the `issubeset` function
    ````
        >> titanic_actors.issubset(hollywood_actors_set)
        False
        >> titanic_actors < hollywood_actors
        False
        >> titanic_actors =< hollywood_actors
        False
        >> titanic_actors < titanic_actors
        False
        >> titanic_actors <= titanic_actors
        True
        ````
- *isDisjoint* of sets
    - isdisjoint function of `True` have any Intersection otherwise `False`
    ````
    >> my_set1 = {'a', 'b', 'c', 'd'}
    >> my_set2 = {'e', 'f', 'i', 'j'}
    >> my_set1.isdisjoint(my_set2)
    False
    >> my_se3 = {'d', 'e', 'f', 'g'}
    my_set1.isdisjoint(my_set3)
    True
    ````
- *POP* function are remove the arbitrary element
    - POP function remove the last item from the sets
    ````
    >> my_set = {"Leaonardo Dicaprio", "Sylvester Stallone", "czechoslovakia", "Tokyo", "Tom Cruise", "Mauritius"}
    >> my_set.pop()
    'czechoslovakia'
    >> my_set.pop() 
    'Leaonardo Dicaprio'
    >> my_set
    {'Tom Cruise', 'Mauritius', 'Tokyo', 'Sylvester Stallone'}
    ````
- *Remove* from the sets
    - Remove function will remove the element from thr sets
    ````
    >> my_set.remove('Sylvester Stallone')
    {'Tom Cruise', 'Mauritius', 'Tokyo'}
    ````

- *Clear* of sets
    - clear all the elements from the list
    ````
    >> my_set.clear()
    >> my_set
    {}
    ````
