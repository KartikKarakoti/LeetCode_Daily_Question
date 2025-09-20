class Router:

    def __init__(self, memoryLimit: int):
        self.n = memoryLimit
        self.packets = deque([])
        self.destinations = defaultdict(deque)
        self.mem = set()
    
    def addPacket(self, s: int, d: int, t: int) -> bool:
        packet = (s, d, t)
        if packet in self.mem: return False
        
        self.packets.append(packet)
        self.mem.add(packet)
        self.destinations[d].append(t)
        
        # remove old values
        if self.n < len(self.packets):
            s, d, t = self.packets.popleft()
            self.mem.remove((s, d, t))
            self.destinations[d].popleft()
        return True

    def forwardPacket(self) -> List[int]:
        if not self.packets: return []
        s, d, t = self.packets.popleft()
        self.mem.remove((s, d, t))
        self.destinations[d].popleft()
        return (s, d, t)
        
    def getCount(self, d: int, s: int, e: int) -> int:
        destination = self.destinations[d]
        left = bisect_left(destination, s)
        right = bisect_right(destination, e)
        return right - left
