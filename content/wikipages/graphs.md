+++
title='Graphs : Some observations and notes'
noComment=true
+++

- Use bfs when possible
- Look out for 0-1 before djikstra
- __Topsort__
	- __kahn's algo__ (when need to preserve order sometimes like UVA 11060, enqueue 0 indegree nodes in a heap process them)
	- simple dfs everywhere else

- __DFS spanning tree__
	- __Back edge__ : explored to explored
	- __Tree edge__ : explored to unexplored

#### Finding __bridges__ and __articulation points__
- If some node is an articulation point then __none of its descendants have a back-edge to any of its ancestors__ . In case it doesn't have any ancestors (when it is root node) then it shouldn't have more than 1 children.

- __tin[node]__ : First time we visit __node__.
- __low[node]__ : lowest __tin[]__ reachable in subtree of __node__
- For articulation point : $low[child]\geq low[node]$
- For bridge : $low[child] > low[node]$
- ##### Implementation:
	```cpp
	void dfs(int node,int p=-1)
	{
		vis[node]=1;
		tin[node]=low[node]=timer++;
		int children=0;
		for(int u:adj[node])
		{
			if(u==p)continue;
			if(vis[u])low[node]=min(low[node],low[u]);
			else
			{
				children++;
				dfs(u,node);
				low[node]=min(low[node],low[u]);
				if(low[u]>=tin[node] and p!=-1)
				{
					//found articulation point
				}
			}
		}
		if(p==-1 and children>1)
		{
			//found articulation point
		}
	}
	```
- In many SCC problems look for property of indegree 0 vertices first.
- Condensed graph is when we substitute SCC with a representative node. 
