# Greedy

## Easy

## Medium

### 881. Boats to Save People

```cpp
class Solution {
public:
    int numRescueBoats(vector<int>& people, int limit) {
        // greedy
        sort(people.begin(), people.end());
        int res, l, r;
        res = l = 0;
        r = people.size() -1;
        while(l <= r){
            if(people[l] + people[r] > limit){
                r--;
            } else {
                r--;
                l++;
            }
            res++;
        }
        return res;
    }
};
```

Sort + two pointers

## Hard
