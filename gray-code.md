
````typescript:
function generateGrayCode(n){
    if (n <= 0){
      return ["0"];
    }
    if(n == 1) {
      return ["0","1"];
    }
    let recAns = generateGrayCode(n - 1);
    let mainAns = [];

    for(let i = 0; i < recAns.length; i++) {
      let s = recAns[i];
      mainAns.push("0" + s);
  
    }
    for(let i = recAns.length - 1; i >= 0; i--) {
      let s = recAns[i];
      mainAns.push("1" + s);
    }
    return mainAns;
}
 
console.log('grayCode ==>', generateGrayCode(3))
````
result: grayCode ==>[
  '000', '001',
  '011', '010',
  '110', '111',
  '101', '100'
]