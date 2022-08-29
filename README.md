import pickle
class Employee:
    def __init__(self,eno,ename,esal,eaddr):
        self.eno=eno
        self.ename=ename
        self.esal=esal
        self.eaddr=eaddr
    def display(self):
        print(self.eno,"\t",self.ename,"\t",self.esal,"\t",self.eaddr)
with open("emp.dat","wb") as f:     #dat means digital audio tap file. files with .dat extention
    e=Employee(100,"sai",100000,"vizag")
    pickle.dump(e,f)
    print("Pickling of employee Object completed...")

with open("emp.dat","rb") as f:
    obj=pickle.load(f)
    print("printing employee information after unpickling")
    obj.display()
