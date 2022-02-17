# Basic
Get everything 
```
jq '.'
```

Get a named property
```
  echo '{"id": 1, "name": "Cam"}' | jq '.id'
```
  



# Array
Find elements where a key (name) contains value(csn_order)
```
curl -s localhost:32311/datastream | jq '.elements[] | select( .name | contains("csn_order" ))'
```

Get an array element by index
```
  echo '[0, 1, 1, 2, 3, 5, 8]' | jq '.[3]'
  # 3
```

Get an array element’s property
```
echo '[{"id": 1, "name": "Mario"}, {"id": 2, "name": "Luigi"}]' | jq '.[1].name'
# Luigi
```

## Slice an array
Slices an array on by index.

```
echo '["a", "b", "c", "d"]' | jq '.[1:3]'
# ["b", "c"]
```

Either the first or last index can be omitted to go from the begining or end.

```
echo '["a", "b", "c", "d"]' | jq '.[1:]'
# ["b", "c", "d"]
```

# Functions
keys
Gets an object’s keys as an array.

```
echo '{ "a": 1, "b": 2 }' | jq 'keys'
# [a, b]
length
```
Gets the length of the array/

```
echo '[0, 1, 1, 2, 3, 5, 8]' | jq 'length'
# 7
```
Or the number of top level keys.

```
echo '{"a": 1, "b": 2}' | jq 'length'
# 2
```
flatten
Condense a nested array into one.

```
echo '[1, 2, [3, 4]]' | jq 'flatten'
# [1, 2, 3, 4]
```
