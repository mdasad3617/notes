```javascript
#brute force
function stockSell(arr){
  let max= 0;
  let high = 0;
  for (var i = 0; i < arr.length; i++) {
    for (var j = i+1; j < arr.length; j++) {
      if (arr[j]>arr[i]) {
        max=arr[j]-arr[i]
        if (high<max) {
          high = max
        }
      }
    }
  }
 return high;
}


