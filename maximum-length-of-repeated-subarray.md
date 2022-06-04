````typescript
// Maximum Length of Repeated Subarray
// Maximum Length of Repeated Subarray
const findMaxLengthRepeated = function (A, B) {
    let n = A.length;
    let m = B.length;
    let dp = new Array(n + 1);
    let isWhile = true;
    let i = 0;
    while (isWhile) {
        if (i === n) {
            isWhile = false;
            break;
        };
        dp[i] = new Array(m + 1);
        for (let j = 0; j <= m; j++)
            dp[i][j] = 0;
        i++;
    }
    let isWhile1 = true;
    let x = n - 1;
    while (isWhile1) {
        if (x < 0) {
            isWhile1 = false;
            break;
        };
        for (let j = m - 1; j >= 0; j--) {
            if (A[x] == B[j])
                dp[j][x] = dp[j + 1][x + 1] + 1;
        }
        x--;
    }
    let maxm = 0;

    for (let i = 0; i < n; i++) {
        for (let j = 0; j < m; j++) {
            maxm = Math.max(maxm, dp[i][j]);
        }
    }
    return maxm;
}

// Driver Code
let A = [1, 2, 3];
let B = [2, 3, 4, 5];
console.log('findMaxLengthRepeated', findMaxLengthRepeated(A, B))
````