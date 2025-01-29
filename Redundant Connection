class Solution:
    def findRedundantConnection(self, edges: List[List[int]]) -> List[int]:
        edges_map = defaultdict(list)

        for edge in edges:
            edges_map[edge[0]].append(edge[1])
            edges_map[edge[1]].append(edge[0])

        visited = set()

        def dfs(node, path, last_node):
            if node in visited: # we found a cycle
                return (True, path)
            visited.add(node)

            adjacents = edges_map[node]

            for new_node in adjacents:
                if new_node == last_node:
                    continue
                found_cycle, new_path = dfs(new_node, path + [new_node], node)
                if found_cycle:
                    return (True, new_path)
            
            return (False, [])
        
        _, path = dfs(1, [1], -1)
        
        # cut the path so that it only contains nodes in the cycle
        for i in range(len(path)):
            if path[i] == path[-1]:
                path = path[i:]
                break

        # if an edge's start and end nodes are both in path, then return it
        for i in range(len(edges) - 1, -1, -1):
            if edges[i][0] in path and edges[i][1] in path:
                return edges[i]
