# Validparentheses

class Solution:
    def isValid(self, s: str) -> bool:
        val = {'}':'{',')':'(',']':'['}
        track = []
        for char in s:
            if char in val:
                len_track = len(track)
                if len_track > 0 and track[len_track-1] == val[char]:
                    track.pop()
                else:
                    return False
            else:
                track.append(char)        
        return (not track)
