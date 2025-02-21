
```javascript
#bruteforece solution

/**
 * @param {number[]} arr
 * @return {number}
 */
var majorityElement = function (arr) {
    let count = 0;
    let lastCount = 0;
    let majElement = -Infinity;
    for (var i = 0; i < arr.length; i++) {
        for (var j = 0; j < arr.length; j++) {
            if (arr[i] == arr[j]) {
                count++;
                if (lastCount < count) {
                    lastCount = count
                    majElement = arr[i]
                }
            }
        }
        count = 0;
    }
    return majElement;
};

#better solution

/**
 * @param {number[]} arr
 * @return {number}
 */



function majorityElement(arr) {
    const n = arr.length;

    const map = new Map();

    for (let i = 0; i < n; i++) {
        const num = arr[i];
        if (map.has(num)) {
            map.set(num, map.get(num) + 1);
        } else {
            map.set(num, 1);
        }
    }

    for (const [num, count] of map) {
        if (count > Math.floor(n / 2)) {
            return num;
        }
    }

    return -1;
}

const arr = [2, 2, 1, 1, 1, 2, 2];
const ans = majorityElement(arr);
console.log("The majority element is:", ans);



#optimised solution

/**
 * @param {number[]} arr
 * @return {number}
 */
var majorityElement = function (arr) {

    let vote = 0;
    let cand = arr[0];
    for (var i = 0; i < arr.length; i++) {
        if (vote == 0) {
            cand = arr[i];
        }
        if (arr[i] == cand) {
            vote++
        }
        if (arr[i] != cand) {
            vote--
        }

    }
    return cand
};
