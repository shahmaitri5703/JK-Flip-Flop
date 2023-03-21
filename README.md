# JK-Flip-Flop
class JKFlipFlop:
    def __init__(self):
        self.q = False
        self.q_bar = True
        self.last_j = False
        self.last_k = False

    def clock(self, j, k):
        if j and not self.last_k:
            self.q = True
            self.q_bar = False
        elif k and not self.last_j:
            self.q = False
            self.q_bar = True
        elif j and self.last_k:
            self.q = True
            self.q_bar = False
        elif k and self.last_j:
            self.q = False
            self.q_bar = True
        self.last_j = j
        self.last_k = k
