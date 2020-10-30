# echo
```
let echo=Echo(ctx,keyfn)

//echo(mes,type)

echo(mes,'c') //center one line
echo(mes,'t') //top one line a|i|u
echo(mes,'m') //message bottom 3line
echo(mes,'s',title,n) //center select10

1-top
2-----
3-title
4-0
5-1
6-2
7-3
8-4
9-5
10-6
11-7
12-8
13-9
14---
15*
16*
17*

```


```
//10 line list

function shop(title,list,type,n){
let is={}
is.array;
is.string;
 let ary=is.string(list)?list.split('\n'):list
 let max=ary.length
 let offset=n //0-(max-10)
 let cursor=n //0-9
 ;

 if(KEY==='^'&&cursor===0) offset+=9;
 if(KEY==='^'&&cursor!=0) cursor--;
 if(KEY==='v'&&cursor===9) offset++;
 if(KEY==='v'&&cursor!=9) cursor++;
 //draw bar
 return (offset%max+cursor)
}




```





















