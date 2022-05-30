
---
title: paiza --B096:爆弾の大爆発
tags: [record, study,コードテスト]
categories: 
- 刷题
index_img: /img/Photo by Meiying Ng.jpg

---
很有意思的题目
难度：easy~medium
---
あなたは今、とある戦略ゲームをプレイしています。
ゲームの中で、敵を攻撃するために、フィールドに爆弾を仕掛けました。
敵がフィールド内に入ったところで一気に爆弾を点火し、敵に攻撃をする寸法です。

フィールドは縦 H 行、横 W 行のマス目としてあらわされ、これらのマス目のうちのいくつかに爆弾が仕掛けてあります。
i 行目、j 列目の爆弾が爆発すると、i 行目全体と j 列目全体に爆風が広がります。
あなたはすでにフィールド上に爆弾を仕掛け終わりました。
フィールド上の爆弾を一気に点火した場合、いくつのマスに爆風が広がるかを計算してください。

例えば、入力例 1 では以下のマスに爆風が広がるため、求めるべきマス目数は 12 になります。

```
入力例1
4 4
#.#.
....
..#.
....
```
```
出力例1
12
```
```
入力例2
5 8
.#.#....
........
........
........
.....#..
```
```
25
```
---
1.需要注意读取有十位数百位数以上。
2.js中字符串不能改变，改成数组

```jsx
process.stdin.resume();
process.stdin.setEncoding('utf8');
// 自分の得意な言語で
// Let's チャレンジ！！
var lines = [];
var reader = require('readline').createInterface({
input: process.stdin,
output: process.stdout
});
reader.on('line', (line) => {
lines.push(line);
});
reader.on('close', () => {
var N=lines[0];

var n = N.substring(0, N.indexOf(" "));

var m = N.substring(N.indexOf(" ")+1,N.length);
//注意一位数以上的索引和截取
const coor = [];
for(let i=1;i<=n;i++){
    for(let j=0; j<=m;j++){
        if(lines[i][j]=='#'){
            coor.push([i,j]);
        }
    }
}//获取坐标炸弹



const result=[];


for(let i=0;i<=n;i++){
    result.push(lines[i].split(''));
}//change to 数组



for(let i=0;i<coor.length;i++){
    var x=coor[i][0];

    for(let j=0;j<m;j++){
        result[x][j]='#';
    }
}//横坐标
for(let i=0;i<coor.length;i++){
    var y= coor[i][1];

    for(let j=1;j<=n;j++){
        if(result[j][y]!='#'){
            result[j][y]='#';
        }

    }
}//纵坐标

var z = 0;
for(let i=0;i<=n;i++){
    for(let j=0;j<=m;j++){
        if(result[i][j]=='#'){
            z++;
        }
    }
}//count z

console.log(z);
});
```
