
void dfs(int v){
    used[v] = 1;
    for(auto to: g[v]){
        if(used[to] == 0){
            p[to] = v;
            dfs(to);
        } else if(used[to] == 2){
            continue;
        } else{
            vector<int> v;
            int x = v;
            while(x != to){
                v.push_back(x);
                x = p[x];
            }
            v.push_back(to);
            for(auto x: v){
                cout << x << ' ';
                exit(0);
            }
        }
    }
    used[v] = 2;
}
