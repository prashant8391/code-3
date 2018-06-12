# code-3
# Middle of linked list
# Class node is defined

class node:

    def __init__(self,data):

        self.data=data
        self.next=None

# Class linked list is defined

class linked_list:

    def __init__(self):

        self.head=None
        
# Function for finding middle of list using traversal method

    def middle1(self):
        count=0
        temp=self.head

        while(temp!=None):
            count=count+1
            temp=temp.next
        t=self.head
        index=int((count+1)/2)
        for i in range(1,index,1):
            t=t.next
            
        return(t.data)

# Function for finding middle of list using two pointers p and q

    def middle(self):

        p=self.head
        q=self.head

        while(q!=None and q.next!=None):
            p=p.next
            q=q.next.next

        return(p.data)

# Function to print data of list

    def print_list(self):
        temp=self.head
        while(temp):
            print(temp.data)
            temp=temp.next

# Function to insert a node    

    def insert(self,new_data):

        new_node=node(new_data)
        temp=self.head

        while(temp!=None and temp.next!=None):
            temp=temp.next

        if(temp!=None):
            temp.next=new_node

        else:
            temp=new_node
            self.head=new_node


if(__name__=='__main__'):

    llist=linked_list()
    llist.insert(180)
    llist.insert(394)
    llist.insert(830)
    llist.insert(1028)
    llist.insert(5922)
    llist.insert(8293)
    print("The linked list is given as:")
    llist.print_list()
    print("The middle node data of the list using traversal method is:",llist.middle1())
    print("The middle node data of the list using pointers method is:",llist.middle())

            
            
        
            
