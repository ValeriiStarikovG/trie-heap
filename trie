class TrieNode:
    def __init__(self):
        self.leaves = {}
        self.bIsEndOfWord = False;
   

class Trie:
    
    def __init__(self):
        self.root = TrieNode()

    # O(n*m)
    def insert(self, word: str) -> None:
         # Start from root
         currNode = self.root
         # For every char in word
         for c in word: # O(n)
             # If there is no c in curNode leaves
             if c not in currNode.leaves: # O(m)
                 # Create new Node in map
                 currNode.leaves[c] = TrieNode()    
             # Change currNode to child of prev Node
             currNode = currNode.leaves[c]
         # Mark this node as the end of word
         currNode.bIsEndOfWord = True

    # O(n*m)
    def search(self, word: str) -> bool:
        # Get needed node
        currNode = self.leavesSearch(word)
        # If currNode is valid
        if currNode != None:
            # return Is it word ot not
            return currNode.bIsEndOfWord
        else:
            # return false
            return False

    # O(n*m)
    def searchPrefix(self, prefix: str) -> bool:
        # Get needed node
        currNode = self.leavesSearch(prefix)
        # if Node is valid
        if currNode != None:
            # Return true
            return True
        # return false
        else:
            return False

    # O(n*m)
    def leavesSearch(self, word: str) -> TrieNode:
         # Start from root
         currNode = self.root
         # For every char in word
         for c in word: # O(n)
             # If there is c in currNode leaves
             if c in currNode.leaves: # O(m)
                 # Change currNode to child of prev node
                 currNode = currNode.leaves[c]
             # Else return null
             else:
                 return None
         # Retun last node after cycle
         return currNode


def Test1_search():
    print("************Test1************")
    print("insert(tb)")
    print("insert(ac)")
    print("insert(table)")
    print()

    trie = Trie()
    trie.insert("tb")
    trie.insert("ac")
    trie.insert("table")

    print("search:")
    print("tb:", trie.search("tb"))
    print("ta:", trie.search("ta"))
    print("ac:", trie.search("ac"))
    print("tabl:", trie.search("tabl"))
    print("table:", trie.search("table"))

def Test2_prefixSearch():
    print("************Test2************")
    print("insert(sum)")
    print("insert(music)")
    print("insert(summer)")
    print("insert(aristotel)")
    print("insert(aristokrat)")
    print("insert(array)")
    print()

    trie = Trie()
    trie.insert("sum")
    trie.insert("music")
    trie.insert("summer")
    trie.insert("aristotel")
    trie.insert("aristokrat")
    trie.insert("array")

    print("prefixSearch:")
    print("s:", trie.searchPrefix("s"))
    print("ar:", trie.searchPrefix("ar"))
    print("af:", trie.searchPrefix("af"))
    print("mus", trie.searchPrefix("mus"))


Test1_search()
print()
Test2_prefixSearch()



