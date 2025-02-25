```javascript


#brute force 
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function (arr) {
    if (arr.length <= 1) {
        return arr[0]
    }
    let maxSum = -Infinity;
    for (var i = 0; i < arr.length; i++) {
        let sum = 0
        for (var j = i; j < arr.length; j++) {
            sum = sum + arr[j]
            if (maxSum < sum) {
                maxSum = sum

            }
        }
    }
    return maxSum;
}



#best approach


function maxNum(arr) {
  let maxSum = -Infinity;
  let sum = 0
  for (var i = 0; i < arr.length; i++) {
    sum+=arr[i];
    if (sum>maxSum) {
      maxSum = sum;
    }
    if (sum<0) {
      sum =0
    }
  }
  return maxSum
}
