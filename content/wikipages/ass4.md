+++
title="Assignment 4"
author="Nikhil"
+++
### __Difference between Sorted Map and Map interface__
- Map is used to store key-value pairs.
- Map is implemented by HashMap and TreeMap.
- SortedMap is implemented by TreeMap.
- Map allows no duplicate values. Keys in a map object must be unique.
- **SortedMap** is a special interface for maintaining all elements in a sorted order. Whereas in a Map order is not fixed only key value mapping is fixed. Sorting process is performed on the map keys.
- **SortedMap** offers an extra non-compiler-checked post condition, i.e. the iterator is sorted.
- The operations SortedMap inherits from Map behave identically on sorted maps and normal maps with two exceptions:

    1. The Iterator returned by the iterator operation on any of the sorted map's Collection views traverse the collections in order.
    2. The arrays returned by the Collection views' toArray operations contain the keys, values, or entries in order.

- SortedMap is Map analog of SortedSet.
- SortedMap is child interface of Map as can be seen in following code:

```java
public interface SortedMap<K,V> extends Map<K,V>{

	Comparator<? super K> comparator();
	SortedMap<K,V> subMap<ap(K fromKey, K toKey);
	SortedMap<K,V> headMap(K toKey);
	SortedMap<K,V> tailMap(K, fromKey);
	K firstKey();
	K lastKey();
}
```

### __Difference between Set and SortedSet__
- **Set** is a collection that cannot contain duplicate elements.
- **Set** models mathematical set abstraction. It contains only methods inherited from __Collection__ and adds the restriction that duplicate elements are prohibited.
- __SortedSet__  interface is a subtype of __Set__ interface. Behaves like a normal set but elements are sorted internally in a natural order or with respect to a comparator.
- When we iterate the elements of __SortedSet__ elements are returned in a sorted manner.

- Code for __SortedSet__ extended from __Set__.
```java
public interface SortedSet<E> extends Set<E> {
    // Range-view
    SortedSet<E> subSet(E fromElement, E toElement);
    SortedSet<E> headSet(E toElement);
    SortedSet<E> tailSet(E fromElement);

    // Endpoints
    E first();
    E last();

    // Comparator access
    Comparator<? super E> comparator();
}

```





