# Mantenimiento y borrado

````
git gc
git count-objects -v

git verify-pack -v .git/objects/pack/pack-177246d8fbd89ec5f1addb7e58ebe322ef27caac.idx \
  | sort -k 3 -n \
  | tail -3

git rev-list --objects --all | grep XXXXX

git log --oneline --branches -- FILE_TO_DELETE

git filter-branch --index-filter \
  'git rm --cached --ignore-unmatch FILE_TO_DELETE' -- ZZZZZZZZ^..

rm -Rf .git/refs/original
rm -Rf .git/logs/
git gc 
`````
Borrado total

````
git prune --expire now
git count-objects -v
````

https://git-scm.com/book/es/v2/Los-entresijos-internos-de-Git-Mantenimiento-y-recuperaci%C3%B3n-de-datos