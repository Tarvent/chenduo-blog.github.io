
---
title: B096:爆弾の大爆発
tags: [record, study,コードテスト]
categories: 
- 刷题
index_img: /img/pexels-sanaan-mazhar-3075993.jpg

---
很有意思的题目
难度：easy~medium


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
