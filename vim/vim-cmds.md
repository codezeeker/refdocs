**--undo**

`u - undo`

`control<mac>+r - redo`

**--delete**

`d$ - delete till end of line`

`dw - delete end of word`

`d100$ - delete next 100 lines`

**\-\- change inside**

`c$ - delete till end of line and open INSERT mode`

**create new document from k8s document using copy paste**

`$ cat > new.yaml  `

`...`

`...PASTE...`

`.....`

`^C`

**goto some line**

`:[line-number]`

`:80`

**Grep a text and show next 10 lines**

`k explain pod.spec --recursive | grep 'env' -A10`

open new line in append mode

cmd+O