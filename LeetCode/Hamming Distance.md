### The Hamming distance between two integers is the number of positions at which the corresponding bits are different.

### Given two integers x and y, calculate the Hamming distance.

### Note:
- 0 ≤ x, y < 231.

```
Example:

Input: x = 1, y = 4

Output: 2

Explanation:
1   (0 0 0 1)
4   (0 1 0 0)
       ↑   ↑

The above arrows point to positions where the corresponding bits are different.
```

---

### Code:

### C++

```
class Solution {
public:
    int hammingDistance(int x, int y) {
        int result=0;
        while(x>0||y>0){
            result += (x%2)^(y%2);
            cout<<"1->"<<x%2<<" "<<y%2<<" "<<x<<" "<<y<<" ->result:"<<result<<endl;
            x>>=1;
            y>>=1;
            cout<<"2->"<<x<<" "<<y<<endl;
        } 
        return result;
    }
};
```

### Other ways:

```
class Solution {
public:
    int hammingDistance(int x, int y) {
     return bitset<32>(x^y).count();
};
```

### Python:

```
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        res = 0
        while x>0 or y>0:
            if(x&0x01) != (y&0x01):
                res-=-1
            x>>=1
            y>>=1
        return res
        
```
