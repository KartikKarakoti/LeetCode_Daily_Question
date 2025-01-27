class Solution:
    def checkIfPrerequisite(self, numCourses: int, prerequisites: List[List[int]], queries: List[List[int]]) -> List[bool]:
        prereq_map = defaultdict(list) # course -> prereqs

        for prereq in prerequisites:
            prereq_map[prereq[1]].append(prereq[0])

        res = []
        memo = {}
        def dfs(course, prereq):
            if (course, prereq) in memo:
                return memo[(course, prereq)]
            
            course_prereqs = prereq_map[course]
            for p in course_prereqs:
                if p == prereq or dfs(p, prereq):
                    memo[(course, prereq)] = True
                    return True
            
            memo[(course, prereq)] = False
            return False
                
        return [dfs(query[1], query[0]) for query in queries]
        
