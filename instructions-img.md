# Mantenimiento y borrado

````
git gc
git count-objects -v

git verify-pack -v .git/objects/pack/pack-480f193e29eb0c959c052711f573cd19efa8afaf.idx\
  | sort -k 3 -n \
  | tail -3

git rev-list --objects --all | grep XXXXX

git log --oneline --branches -- FILE_TO_DELETE

git filter-branch --index-filter \
  'git rm --cached --ignore-unmatch img.png' -- af86445^..

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

