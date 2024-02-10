class Solution:
    def openLock(self, deadends: List[str], target: str) -> int:
        
        toIgnore = set(deadends)
        index = 0
        graphe = (["0000"])

        def nextStep(position):
            return (position + 1) % 10, (position + 9) % 10
        def childrens(node):
            childs = []
            for i in range(4):
                r, l = nextStep(int(node[i]))
                child1 = node[:i] + str(r) + node[i+1:]
                child2 = node[:i] + str(l) + node[i+1:]
                childs.append(child1)
                childs.append(child2)
            return childs

        end = set([target])

        while graphe and end:
            temp = set()
            for node in graphe:
                if node in toIgnore:
                    continue
                if node in end:
                    return index
                toIgnore.add(node)  
                temp.update(childrens(node))
            index += 1
            graphe = end
            end = temp
        
        return -1
