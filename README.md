# echo
message split
```
//文字サイズを指定して、改行と、最大数で文字列を改行する。

let test=`
　君たちは、幾つかに目を瞑って、そうであると思わなければならない。
　この世界には魔法がある。魔法の存在証明は幾つかあるが、それを否定することは難しい。しかし、曖昧にも曖昧すぎる話だ。わかりやすいものをまず提示しよう。
　これは、鍛冶屋の喩え、と呼ばれる。喩え（たとえ）とは、ここでは寓話と思ってもらって構わない。
　こんな話だ――。

　――狼や大型の獣を狩るのによ、犬鷲を商ってたことがあるんだ。犬鷲ってのは、王侯貴族の狩猟に使われるもので、云ってみれば娯楽用途の狩猟だな、犬鷲は翼長が全て広がれば、人間が両腕を広げたよりも大きい。翼の端から端まで持てないほどだ。犬鷲は、人間と同じ大きさってことだな。俺はその後、めでたく鍛冶屋になって武器を作ることになったんだが、ツーハンデッドソードって知ってるか、大型の両刃剣だな。これはオーガ狩りなんかに使われる大剣で、犬鷲と同じ大きさなんだが、これを作るために必要なインゴットは腕の長さくらいの鉄の塊なんだ。犬鷲と同じ重さ。つまり、犬鷲ってのは、人間並に、大きい癖には、重さが妙に軽い生き物ってことだな。俺はこれが空を飛ぶ秘訣だと思っていたのさ。
　――ある時、俺は、そんな秘訣を語りながら、店で冒険者の話し相手をしていた。すると冒険者は面白い事を云うんだ。それは軽いもの程、空を飛ぶ可能性があるという事だろうけれど、それはおかしくないか？ってな。いやいや、おかしいわけ無いだろ。俺は、犬鷲の重さを実によく知っているし、インゴットの重さも知っている――。だが、その冒険者は、こう続けた。僕は犬鷲よりも、インゴットよりも、この店、そして、迷宮全体の全ての重さでさえあっても可能な、空飛ぶものを知っている。
　――俺はもちろん、反論したね。鳥ってのは効率に効率を突き詰めてようやく飛ぶってことを獲得したんだ。骨なんて、こいつらダシに使えば鍋の上に浮くくらいだし、羽の軽さは云うまでもない。しかし、その冒険者は空を指してこう云った。これさ――。俺は少し考えたが、丁度雲海が開き、雲が晴れ、広大な、一切のない空が見えた時に悟ったね。浮遊大陸か――。俺はこれは何か鳥とは別の原理で出来ていると気づいた。
　――魔法だ。
`
String.prototype.echo=function(n){
 //let time=performance.now()
 n=n||24;
 let str=this
 let str2=str.replace(/、/g,'、\n').replace(/。/g,'。\n').replace(/\n\n/g,'\n')
 //console.log(str2)
 let f=(d)=>{
  let ary=[]
  let d0=''
  let d1=d.slice(0,n)
  let d2=d.slice(n)
  if(d.charAt(0)==='　')ary.push(d0)
  ary.push(d1)
  if(d2)ary.push(d2)
  return ary
 }
 
 let ary=str2.split('\n').map(f).flat().join('\n').replace(/\n\n\n/g,'\n\n').split('\n')
 let ret=[],r=0,i
 for(i=0;i<ary.length;i++){
  let d=ary[i]
  if(!ret[r]){
   ret[r]=d
   if(/。/.test(d)||d.length===0) r++;
   continue
  }else{
   if(ret[r].length + d.length > n) r++,ret[r]='';
   ret[r]=ret[r]+d
   if(/。/.test(d)||d.length===0) r++;
   continue   
  }
 }
 
 //console.log(performance.now()-time)
 return ret//ary
}

/*
let i=0,dat=test.echo(24),log=[]

console.log(dat)
fn.q('pre').textContent=dat.join('\n')
*/
```
