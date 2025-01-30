class Solution:
    def magnificentSets(self, n: int, edges: List[List[int]]) -> int:
        graph = [[] for _ in range(n)]
        for u, v in edges: 
            graph[u-1].append(v-1)
            graph[v-1].append(u-1)
        
        seen = [0]*n
        group = []
        for i in range(n): 
            if not seen[i]: 
                seen[i] = 1
                stack = [i]
                group.append([i])
                while stack: 
                    u = stack.pop()
                    for v in graph[u]: 
                        if not seen[v]: 
                            seen[v] = seen[u] + 1
                            stack.append(v)
                            group[-1].append(v)
                        elif seen[u] & 1 == seen[v] & 1: return -1

        def bfs(x): 
            """Return the levels starting from x."""
            ans = 0
            seen = {x}
            queue = deque([x])
            while queue: 
                ans += 1
                for _ in range(len(queue)): 
                    u = queue.popleft()
                    for v in graph[u]: 
                        if v not in seen: 
                            seen.add(v)
                            queue.append(v)
            return ans 
                            
        ans = 0 
        for g in group: ans += max(bfs(x) for x in g)
        return ans 
