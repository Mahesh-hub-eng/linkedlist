class node:
    def __init__(self,x,nxt):
        self.data=x
        self.next=nxt
class llist:
    def __init__(self):
        self.head=None
        self.tail=None
    def insert(self,x):
        a=node(x,None)
        if self.head==None:
            self.head=a
            self.tail=a
        else:
            self.tail.next=a
            self.tail=a
    def infirst(self,x):
        l=self.length()
        a=node(x,None)
        if self.head==None:
            self.head=a
            self.tail=a
        else:
            a.next=self.head
            self.head=a
    def delfirst(self):
        if self.head==None:
            print("No elements to delete")
        else:
            t=self.head
            print("the deleted element is ",t.data)
            n=self.head.next
            self.next=None
            self.head=n
    def dellast(self):
        if self.head==None:
            print("no elements to delete")
        else:
            t=self.head
            while (t.next!=None):
                n=t
                t=t.next
            print("The deleted element is",t.data)
            n.next=None
            self.tail=n
    def delinpos(self,pos):
        l=self.length()
        if pos>l:
            print("invalid")
        else:
            n1=self.head
            n2=self.head
            i=1
            while i<pos:
                n1=n2
                n2=n2.next
                i+=1
            n=n2.next
            n1.next=n           
    def length(self):
        if self .head==None:
            return 0
        else:
            t=self.head
            c=0
            while t!=None:
                c+=1
                t=t.next
            return c
    def inpos(self,x,pos):
        l=self.length()
        if (pos>l):
            print("invalid")
        else:
            a=node(x,None)
            n1=self.head
            n2=self.head
            i=1
            while i<pos:
                n1=n2
                n2=n2.next
                i+=1
            a.next=n2
            n1.next=a
    def traverse(self):
        temp=self.head
        if temp==None:
            print("no")
        else:
            while temp!=None:
                print(temp.data)
                temp=temp.next
l=llist()

while(True):
    print("Enter your choice")
    print("1.Insert at last")
    print("2.Insert at first")
    print("3.Insert at position")
    print("4.Delete first")
    print("5.Delete last")
    print("6.Delete position")
    print("7.Display")
    print("8.Exit")
    ch=int(input(""))
    if(ch==1):
        x=int(input("Enter to insert at last"))
        l.insert(x)
        print("Value inserted at last")
    elif(ch==2):
        x=int(input("Enter to insert at first"))
        l.infirst(x)
        print("Value inserted at first")
    elif(ch==3):
        x=int(input("Enter value to insert"))
        pos=int(input("Enter the position"))
        l.inpos(x,pos)
    elif(ch==4):
        l.delfirst()
    elif(ch==5):
        l.dellast()
    elif(ch==6):
        pos=int(input("Enter the position"))
        l.delinpos(pos)
    elif(ch==7):
        l.traverse()    
    elif(ch==8):
        print("exit")
        break
    else:
        print("Invalid Choice")
