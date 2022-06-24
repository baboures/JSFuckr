## JSFuckr: An esoteric language based on JSFuck

Try it online: https://baboures.github.io/tools/jsfuckr/

**Features**
- You can encode JavaScript using only six chars `([+<])`
- It's a modification of [JSFuck](http://jsfuck.com) that uses `<` instead of `!`

**How it works** (see the [full mapping](https://github.com/baboures/JSFuckr/blob/master/MAPPING.json) or a [step-by-step example](https://github.com/aemkei/jsfuck/issues/122#issuecomment-1164710384))

```js

// Primitives
'false':      '([]<[])'
'true':       '([]<[+[]])'
'undefined':  '[][[]]'
'NaN':        '+[[]<[]]'
'Infinity':   '+([+([]<[+[]])]+(([]<[+[]])+[])[([]<[+[]])+([]<[+[]])+([]<[+[]])]+[+([]<[+[]])]+[+[]]+[+[]]+[+[]])' // +"1e1000"
  
// Constructors
'Array':    '[]'
'Number':   '(+[])'
'String':   '([]+[])'
'Boolean':  '([]<[])'
'Function': '[]["flat"]'
'RegExp':   'Function("return/"+false+"/")()'
'Object':   '[]["entries"]()'

// Numbers in the range 0-9
0: +[]
1: +([]<[+[]])
2: ([]<[+[]])+([]<[+[]])
3: ([]<[+[]])+([]<[+[]])+([]<[+[]])
4: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])
5: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])
6: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])
7: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])
8: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])
9: ([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])+([]<[+[]])

// Numbers greater than 9
'10': +([]<[+[]])+[+[]]
'11': +([]<[+[]])+[+([]<[+[]])]
'12': +([]<[+[]])+[([]<[+[]])+([]<[+[]])]
'100': +([]<[+[]])+[+[]]+[+[]]
'123': +([]<[+[]])+[([]<[+[]])+([]<[+[]])]+[([]<[+[]])+([]<[+[]])+([]<[+[]])]
```

[Read compiler source](https://github.com/baboures/JSFuckr/blob/master/JSFuckr.js)
