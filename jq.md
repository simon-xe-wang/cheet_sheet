Get a named property
```
  echo '{"id": 1, "name": "Cam"}' | jq '.id'``
```
  
Get an array element by index
```
  echo '[0, 1, 1, 2, 3, 5, 8]' | jq '.[3]'
  # 3
```
