# Data-Structures
All Data Structures Code from scratch
#Linked List
def findMidNode(A):
    if A==None or A.next == None:
        return A
    slow = A
    fast = A
    while(fast.next != None and fast.next.next != None):
        slow = slow.next
        fast = fast.next.next
    return slow
    
def reverseList(A):
    if A==None or A.next == None:
         return A 
    prev  = A 
    curr1 = A.next
    while(curr1 != None):
        Next = curr1.next
        curr1.next= prev
        prev = curr1
        curr1= Next

    A.next=None 
    return prev
    
class Node:
    def __init__(self,val):
        self.val= val
        self.next= None
        
        
class List:
    def __init__(self):
        self.head = None
        self.tail = None
        self.size = 0
    
    def insertAtHead(self, val):
        newNode = Node(val)
        if self.size == 0:
            self.head = newNode
            self.tail = newNode
        else:
            newNode.next= self.head
            self.head=newNode
        self.size+=1
        
    def printLL(self):
        temp = self.head
        while(temp!= None):
            print(temp.val,end=' ')
            temp = temp.next
            
l1 = List()
l1.insertAtHead(5)
l1.insertAtHead(4)
l1.insertAtHead(3)
l1.insertAtHead(2)
l1.insertAtHead(1)
print('before')
l1.printLL()
print('after reverse')
l1.head=reverseList(l1.head)
l1.printLL()
print(l1.head.val)
#mid = findMidNode(l1.head)
#print(mid.val)


        
        
        
    
