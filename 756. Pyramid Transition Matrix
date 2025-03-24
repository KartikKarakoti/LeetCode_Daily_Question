class Solution:
		def get_states(self,s,i,new,allowed):
			if i==len(s):
				self.res.append(''.join(new))
				return 
			for x in allowed[s[i-1]+s[i]]:
				new.append(x)
				self.get_states(s,i+1,new,allowed)
				new.pop()

		def pyramidTransition(self, bottom: str, allowed: List[str]) -> bool:
			a=defaultdict(list)
			for s in allowed:
				a[s[:2]].append(s[2])
			self.res=[bottom]
			for x in self.res:
				if len(x)==1:
					return True
				self.get_states(x,1,[],a)
			return False
			
