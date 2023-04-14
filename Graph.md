# Graph

## Easy

## Medium

### 1254. Number of Closed Islands

```cpp
class Solution {
private:
    int row, col;
    vector<int> dir{1,0,-1,0,1};
public:
    int closedIsland(vector<vector<int>>& grid) {
        int res = 0;
        row = grid.size();
        col = grid[0].size();
        bool isClosed = true;
        for(int i = 0;i < row; i++){
            for(int j = 0; j < col; j++){
                if(grid[i][j] == 1) continue;
                isClosed = true;
                dfs(grid, i, j, isClosed);
                if(isClosed){
                    res++;
                }
            }
        }
        return res;
    }

    void dfs(vector<vector<int>>& grid,int i, int j, bool& isClosed) {
        if(i >= row || j >= col || i < 0 || j < 0) return;
        if(grid[i][j] == 1) return;
        grid[i][j] = 1;
        if(i * j == 0 || i == row-1 || j == col-1) isClosed = false;
        for(int k = 0; k < 4; k++){
            dfs(grid, i+dir[k], i+dir[k+1], isClosed);
        }
    }
};
```

Key: dfs to find the cell that reach the border

## Hard
