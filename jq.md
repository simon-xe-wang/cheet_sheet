Get a named property
```
  echo '{"id": 1, "name": "Cam"}' | jq '.id'``
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


Slice an array
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
