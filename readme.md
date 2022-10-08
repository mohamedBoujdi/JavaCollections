# Collection framework
1. [x] **Collection is an interface**
2. [x] **implementing interfaces**
    - **List**
      - **ArrayList**
      - **LinkedList**
      - **Vector**
    - **Set**
      - **HashSet**
      - **LinkedHashSet**
      - **TreeSet**
    - **Queue**
      - **PriorityQueue**
      - **LinkedList**
      - **ArrayDeque**
    - **Map**
      - **HashMap**
      - **LinkedHashMap**
      - **TreeMap**
      - **Hashtable**
      - **properties**
>new Collection framework in java 17 is added in the list
  > - EnumMap : for enum keys
  > - ConcurrentHashMap : for concurrent access
  > - ConcurrentSkipListMap : for concurrent access also and skip list data structure (which means it is sorted)
  > - WeakHashMap  : for garbage collection (when the key is not used anymore, it will be removed from the map)
  > - IdentityHashMap  : for comparing the keys by reference (==) not by equals
    
## **Collection framework hierarchy**

### **List --> ArrayList, LinkedList, Vector (List is an interface)**
#### ArrayList : dynamic array implementation of List
##### example:(casting is not needed)
```java

ArrayList<String> arrayList = new ArrayList<>();
arrayList.add("a");
arrayList.add("b");
arrayList.add("c");
arrayList.add("d");

System.out.println(arrayList);
// output: [a, b, c, d]
```
##### cracteristics:
       -  default size 10
       -  not thread safe:means multiple threads can access it at the same time (not synchronized)
       -  faster:why? because it is not synchronized
       -  can contain duplicate elements (elements are not unique)
       -  can contain null elements (only one null element e.g. [null, 1, 2, 3])
       -  can be accessed using index (e.g. list.get(0))
       -  not ordered: means it does not maintain the order of insertion
       -  ArrayList is the best choice if you want to access elements by index
       -  ArrayList is the worst choice if you want to insert or delete elements from the middle of the list
       -  ArrayList is the worst choice if you want to iterate through the list
       -  ArrayList is the worst choice if you want to sort the list
       -  ArrayList is the worst choice if you want to search the list
       -  ArrayList is the worst choice if you want to access elements randomly
       -  ArrayList is the worst choice if you want to access elements in reverse order
#### LinkedList : double linked list implementation of List (doubly linked list)
##### example: (casting is needed)
```java

LinkedList<String> linkedList = new LinkedList<>();
linkedList.add("a");
linkedList.add("b");
linkedList.add("c");
linkedList.add("d");
 
System.out.println(linkedList)
// output: [a, b, c, d]
```
##### cracteristics:
       - not thread safe
       - can contain duplicate elements
       - can contain null elements
       - can be accessed using index (e.g. list.get(0))
       - ordered: means it maintains the order of insertion
       - LinkedList is the worst choice if you want to access elements by index
       - (e.g. for(int i = 0; i < list.size(); i++) { System.out.println(list.get(i)); })
       - LinkedList is the best choice if you want to insert or delete elements from the middle of the list
       - LinkedList is the best choice if you want to iterate through the list (faster than ArrayList)
       - LinkedList is the worst choice if you want to search the list
       - LinkedList is the worst choice if you want to access elements randomly
       - LinkedList is the worst choice if you want to sort the list
#### Vector (legacy class and not recommended) 
##### example: (casting is needed)
```java
Vector<String> vector = new Vector<>();
vector.add("a");
vector.add("b");
vector.add("c");
vector.add("d");

System.out.println(vector);
// output: [a, b, c, d]
```
##### cracteristics:

       -thread safe (synchronized) means only one thread can access it at the same time
       -can contain duplicate elements
       -can contain null elements
       -can be accessed using index (e.g. list.get(0))
       -ordered: means it maintains the order of insertion
       -Vector is the best choice if you want to access elements by index
       -Vector is the worst choice if you want to insert or delete elements from the middle of the list
       -Vector is the worst choice if you want to iterate through the list
       -Vector is the worst choice if you want to sort the list
       -Vector is the worst choice if you want to search the list
       -Vector is the worst choice if you want to access elements randomly
       -Vector is the worst choice if you want to access elements in reverse order
       -Vector is the worst choice if you want to access elements by index
### Set --> HashSet, LinkedHashSet, TreeSet (Set is an interface)
#### HashSet (why hash? because it uses hash table internally)
##### example: (casting is not needed)
```java
HashSet<String> hashSet = new HashSet<>();
hashSet.add("a");
hashSet.add("b");
hashSet.add("c");
hashSet.add("d");
    
System.out.println(hashSet);
// output: [a, b, c, d]
```
##### cracteristics:

       -hash table is a data structure that uses hash function to store and retrieve data
       -not thread safe (not synchronized) means multiple threads can access it at the same time
       -can not contain duplicate elements (elements are unique)
       -can contain null elements (only one null element e.g. [null, 1, 2, 3])
       -can not be accessed using index (e.g. set.get(0)) (no index)
       -not ordered: means it does not maintain the order of insertion
       -HashSet is the best choice if you want to search the set
       -HashSet is the best choice if you want to check if an element exists in the set
       -HashSet is the best choice if you want to add or remove elements from the set
       -HashSet is the worst choice if you want to access elements by index
       -HashSet is the worst choice if you want to iterate through the set
       -HashSet is the worst choice if you want to sort the set
       -HashSet is the worst choice if you want to access elements randomly
       -HashSet is the worst choice if you want to access elements in reverse order
#### LinkedHashSet (why linked and Hash? because it uses linked list and hash table internally)
##### example: (casting is not needed)
```java
LinkedHashSet<String> linkedHashSet = new LinkedHashSet<>();
linkedHashSet.add("a");
linkedHashSet.add("b");
linkedHashSet.add("c");
linkedHashSet.add("d");
System.out.println(linkedHashSet);
// output: [a, b, c, d]
```
##### cracteristics:

        -not thread safe (not synchronized) means multiple threads can access it at the same time
        -can not contain duplicate elements
        -can contain null elements
        -can not be accessed using index
        -ordered: means it maintains the order of insertion
        -LinkedHashSet is the best choice if you want to access elements by index
        -LinkedHashSet is the best choice if you want to iterate through the set
        -LinkedHashSet is the worst choice if you want to search the set
        -LinkedHashSet is the worst choice if you want to check if an element exists in the set
        -LinkedHashSet is the worst choice if you want to add or remove elements from the set
        -LinkedHashSet is the worst choice if you want to sort the set
        -LinkedHashSet is the worst choice if you want to access elements randomly
        -LinkedHashSet is the worst choice if you want to access elements in reverse order
#### TreeSet  (why tree? because it uses tree data structure internally)
##### example: (casting is not needed)
```java
TreeSet<String> treeSet = new TreeSet<>();
treeSet.add("a");
treeSet.add("b");
treeSet.add("c");
treeSet.add("d");
System.out.println(treeSet);
// output: [a, b, c, d]
```
##### caacteristics:
        
       - tree data structure is a data structure that uses a tree to store and retrieve data
       - not thread safe
       - can not contain duplicate elements
       - can not contain null elements
       - can not be accessed using index (e.g. set.get(0)) (no index)
       - ordered: means it maintains the order of insertion
       - TreeSet is the best choice if you want to access elements by index
       - TreeSet is the best choice if you want to iterate through the set
       - TreeSet is the best choice if you want to sort the set
       - TreeSet is the worst choice if you want to search the set
       - TreeSet is the worst choice if you want to check if an element exists in the set
       - TreeSet is the worst choice if you want to add or remove elements from the set
       - TreeSet is the worst choice if you want to access elements randomly
       - TreeSet is the worst choice if you want to access elements in reverse order
       - TreeSet is the worst choice if you want to access elements by index
### Map --> HashMap, LinkedHashMap, TreeMap, Hashtable, Properties (Map is an interface)
why map? because it uses key-value pairs to store and retrieve data (e.g. {key1=value1, key2=value2})
 #### HashMap (why hash? because it uses hash table internally)
    ##### example: (casting is not needed)
```java
HashMap<String, String> hashMap = new HashMap<>();  
hashMap.put("key1", "value1");
hashMap.put("key2", "value2");
hashMap.put("key3", "value3");
hashMap.put("key4", "value4");
System.out.println(hashMap);
// output: {key1=value1, key2=value2, key3=value3, key4=value4}
```
##### cracteristics:

       - not thread safe (not synchronized) means multiple threads can access it at the same time
       - can not contain duplicate keys (keys are unique)
       - can contain null keys (only one null key e.g. [null, 1, 2, 3])
       - can contain duplicate values (values are not unique)
       - can contain null values (multiple null values e.g. [1, 2, 3, null, null])
       - can be accessed using key (e.g. map.get("key"))
       - not ordered: means it does not maintain the order of insertion
       - HashMap is the best choice if you want to search the map
       - HashMap is the best choice if you want to check if a key exists in the map
       - HashMap is the best choice if you want to add or remove elements from the map
       - HashMap is the worst choice if you want to access elements by index
       - HashMap is the worst choice if you want to iterate through the map
       - HashMap is the worst choice if you want to sort the map
       - HashMap is the worst choice if you want to access elements randomly
       - HashMap is the worst choice if you want to access elements in reverse order
#### LinkedHashMap not thread safe (not synchronized) means multiple threads can access it at the same time                          
 ##### example: (casting is not needed)
```java
LinkedHashMap<String, String> linkedHashMap = new LinkedHashMap<>();
linkedHashMap.put("key1", "value1");
linkedHashMap.put("key2", "value2");
linkedHashMap.put("key3", "value3");
linkedHashMap.put("key4", "value4");
System.out.println(linkedHashMap);
// output: {key1=value1, key2=value2, key3=value3, key4=value4}
```
##### cracteristics:

      -can not contain duplicate keys           
      -can contain null keys
      - can contain duplicate values
      - can contain null values
      - can be accessed using key (e.g. map.get("key"))
      - ordered: means it maintains the order of insertion
      - LinkedHashMap is the best choice if you want to access elements by index
      - LinkedHashMap is the best choice if you want to iterate through the map
      - LinkedHashMap is the worst choice if you want to search the map
      - LinkedHashMap is the worst choice if you want to check if a key exists in the map
      - LinkedHashMap is the worst choice if you want to add or remove elements from the map
      - LinkedHashMap is the worst choice if you want to sort the map
      - LinkedHashMap is the worst choice if you want to access elements randomly
      - LinkedHashMap is the worst choice if you want to access elements in reverse order
#### TreeMap
##### example: (casting is not needed)
```java
TreeMap<String, String> treeMap = new TreeMap<>();
treeMap.put("key1", "value1");
treeMap.put("key2", "value2");
treeMap.put("key3", "value3");
treeMap.put("key4", "value4");
System.out.println(treeMap);
// output: {key1=value1, key2=value2, key3=value3, key4=value4}
```
##### cracteristics:

      -not thread safe
      -can not contain duplicate keys
      -can not contain null keys
      -can contain duplicate values
      -can contain null values
      -can be accessed using key (e.g. map.get("key"))
      -ordered: means it maintains the order of insertion
      -TreeMap is the best choice if you want to access elements by index
      -TreeMap is the best choice if you want to iterate through the map
      -TreeMap is the best choice if you want to sort the map
      -TreeMap is the worst choice if you want to search the map
      -TreeMap is the worst choice if you want to check if a key exists in the map
      -TreeMap is the worst choice if you want to add or remove elements from the map
      -TreeMap is the worst choice if you want to access elements randomly
      -TreeMap is the worst choice if you want to access elements in reverse order
#### Hashtable
##### example: (casting is not needed)
```java
Hashtable<String, String> hashtable = new Hashtable<>();
hashtable.put("key1", "value1");
hashtable.put("key2", "value2");
hashtable.put("key3", "value3");
hashtable.put("key4", "value4");
System.out.println(hashtable);
// output: {key1=value1, key2=value2, key3=value3, key4=value4}
```
##### cracteristics:

      - thread safe (synchronized) means multiple threads can not access it at the same time
      - can not contain duplicate keys
      - can not contain null keys
      - can contain duplicate values
      - can contain null values
      - can be accessed using key (e.g. map.get("key"))
      - not ordered: means it does not maintain the order of insertion
      - Hashtable is the best choice if you want to search the map
      - Hashtable is the best choice if you want to check if a key exists in the map
      - Hashtable is the best choice if you want to add or remove elements from the map
      - Hashtable is the worst choice if you want to access elements by index
      - Hashtable is the worst choice if you want to iterate through the map
      - Hashtable is the worst choice if you want to sort the map
      - Hashtable is the worst choice if you want to access elements randomly
      - Hashtable is the worst choice if you want to access elements in reverse order
#### Properties  (why properties? because it is used to read and write properties files)
##### example: (casting is not needed)
```java
Properties properties = new Properties();
properties.put("key1", "value1");
properties.put("key2", "value2");
properties.put("key3", "value3");
properties.put("key4", "value4");
System.out.println(properties);
// output: {key1=value1, key2=value2, key3=value3, key4=value4}
```
##### cracteristics:

      -thread safe (synchronized) means multiple threads can not access it at the same time
      -can not contain duplicate keys
      -can not contain null keys
      -can contain duplicate values
      -can contain null values
      -can be accessed using key (e.g. map.get("key"))
      -not ordered: means it does not maintain the order of insertion
      -Properties is the best choice if you want to search the map
      -Properties is the best choice if you want to check if a key exists in the map
      -Properties is the best choice if you want to add or remove elements from the map
      -Properties is the worst choice if you want to access elements by index
      -Properties is the worst choice if you want to iterate through the map
      -Properties is the worst choice if you want to sort the map
      -Properties is the worst choice if you want to access elements randomly
      -Properties is the worst choice if you want to access elements in reverse order
      -Properties is the worst choice if you want to access elements by index
      -Properties is the best choice if you want to read and write properties files
      -Properties is the worst choice if you want to read and write xml files
      -Properties is the worst choice if you want to read and write json files
      -Properties is the worst choice if you want to read and write csv files
      -Properties is the worst choice if you want to read and write excel files
      -Properties is the worst choice if you want to read and write pdf files
      -Properties is the worst choice if you want to read and write text files
      -Properties is the worst choice if you want to read and write binary files
      -Properties is the worst choice if you want to read and write images
      -Properties is the worst choice if you want to read and write videos
      -Properties is the worst choice if you want to read and write audio files
      -Properties is the worst choice if you want to read and write database files
      -Properties is the worst choice if you want to read and write database tables
### Queue --> LinkedList, PriorityQueue, ArrayDeque
why queue? because it is used to store the elements in the order of insertion
  #### LinkedList 
##### example: (casting is not needed)
```java
Queue<String> queue = new LinkedList<>();
queue.add("value1");
queue.add("value2");
queue.add("value3");
queue.add("value4");
System.out.println(queue);
// output: [value1, value2, value3, value4]
```
##### cracteristics:

        -not thread safe (not synchronized) means multiple threads can access it at the same time
        -can contain duplicate elements
        -can contain null elements
        -can be accessed using index (e.g. list.get(0))
        -ordered: means it maintains the order of insertion
        -LinkedList is the best choice if you want to access elements by index
        -LinkedList is the best choice if you want to iterate through the list
        -LinkedList is the best choice if you want to add or remove elements from the list
        -LinkedList is the worst choice if you want to search the list
        -LinkedList is the worst choice if you want to check if an element exists in the list
        -LinkedList is the worst choice if you want to sort the list
        -LinkedList is the worst choice if you want to access elements randomly
        -LinkedList is the worst choice if you want to access elements in reverse order
#### PriorityQueue
##### example: (casting is not needed)
```java
Queue<String> queue = new PriorityQueue<>();
queue.add("value1");
queue.add("value2");
queue.add("value3");
queue.add("value4");
System.out.println(queue);
// output: [value1, value2, value3, value4]
```
##### cracteristics:

        -not thread safe (not synchronized) means multiple threads can access it at the same time
        -can contain duplicate elements
        -can contain null elements
        -can be accessed using index (e.g. list.get(0))
        -ordered: means it maintains the order of insertion
        -PriorityQueue is the best choice if you want to access elements by index
        -PriorityQueue is the best choice if you want to iterate through the list
        -PriorityQueue is the best choice if you want to add or remove elements from the list
        -PriorityQueue is the worst choice if you want to search the list
        -PriorityQueue is the worst choice if you want to check if an element exists in the list
        -PriorityQueue is the worst choice if you want to sort the list
        -PriorityQueue is the worst choice if you want to access elements randomly
        -PriorityQueue is the worst choice if you want to access elements in reverse order
#### ArrayDeque
##### example: (casting is not needed)
```java
Queue<String> queue = new ArrayDeque<>();
queue.add("value1");
queue.add("value2");
queue.add("value3");
queue.add("value4");
System.out.println(queue);
// output: [value1, value2, value3, value4]
```
##### cracteristics:

        -not thread safe (not synchronized) means multiple threads can access it at the same time
        -can contain duplicate elements
        -can contain null elements
        -can be accessed using index (e.g. list.get(0))
        -ordered: means it maintains the order of insertion
        -ArrayDeque is the best choice if you want to access elements by index
        -ArrayDeque is the best choice if you want to iterate through the list
