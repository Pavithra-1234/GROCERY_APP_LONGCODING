# GROCERY_APP_LONGCODING
class GroceryApp:
    def __init__(self):
        self.user_lists=[]
    def start(self):
        name=input("ENTER YOUR NAME: ")
        phoneno=input("ENTER YOUR PHONENO: ")
        password=input("ENTER YOUR PASSWORD: ")
        user=Registration.register(name,phoneno,password,self.user_lists)
        if user==None:
            user=Registration.login(phoneno,password,self.user_lists) 
        print("1.FRUIT\n2.VEGETABLES\n3.SNACKS\n4.ORDER\n5.CART")
        user_choice=input("ENTER YOUR CHOICE: ")
        if(user_choice.lower()=="fruit"):
            fruits_list=[]
            fruits_list.append(Fruit("POMEGRANATE","200","1 KG","30 DAYS","5 DAYS"))
            fruits_list.append(Fruit("WATERMELON","200","5 KG","30 DAYS","20 DAYS"))
            fruits_list.append(Fruit("APPLE","250","1 KG","30 DAYS","2 DAYS"))
            fruits_list.append(Fruit("ORANGE","400","3 KG","30 DAYS","15 DAYS"))
            for i in fruits_list:
                print(i.name)
            fruit_choice=input("ENTER YOUR CHOICE: ")
            for i in fruits_list:
                if i.name==fruit_choice.upper():
                    i.details()
        if(user_choice.lower()=="vegetables"):
            fruits_list=[]
            fruits_list.append(Vegetables("CARROT","200","1 KG","30 DAYS","5 DAYS"))
            fruits_list.append(Vegetables("BEANS","200","5 KG","30 DAYS","20 DAYS"))
            fruits_list.append(Vegetables("POTATO","250","1 KG","30 DAYS","2 DAYS"))
            fruits_list.append(Vegetables("PUMKIN","400","3 KG","30 DAYS","15 DAYS"))
            for i in fruits_list:
                print(i.name)
            fruit_choice=input("ENTER YOUR CHOICE: ")
            for i in fruits_list:
                if i.name==fruit_choice.upper():
                    i.details()
        if(user_choice.lower()=="snacks"):
            fruits_list=[]
            fruits_list.append(Snacks("CHIPS","200","1 KG","30 DAYS","5 DAYS"))
            fruits_list.append(Snacks("BISCUIT","200","5 KG","30 DAYS","20 DAYS"))
            fruits_list.append(Snacks("POPCORN","250","1 KG","30 DAYS","2 DAYS"))
            fruits_list.append(Snacks("CAKE","400","3 KG","30 DAYS","15 DAYS"))
            for i in fruits_list:
                print(i.name) 
            fruit_choice=input("ENTER YOUR CHOICE: ")
            for i in fruits_list:
                if i.name==fruit_choice.upper():
                    i.details()

class Fruit:
    def __init__(self,name,price,quantity,freshness,expiry):
        self.name=name
        self.price=price
        self.quantity=quantity
        self.freshness=freshness
        self.expiry=expiry
    def details(self):
        print("THE DETAILS OF THE FRUIT: ",self.name,self.price,self.quantity,self.freshness,self.expiry)
class Vegetables:
    def __init__(self,name,price,quantity,freshness,expiry):
        self.name=name
        self.price=price
        self.quantity=quantity
        self.freshness=freshness
        self.expiry=expiry
    def details(self):
        print("THE DETAILS OF THE VEGETABLES: ",self.name,self.price,self.quantity,self.freshness,self.expiry)
class Snacks:
    def __init__(self,name,price,quantity,freshness,expiry):
        self.name=name
        self.price=price
        self.quantity=quantity
        self.freshness=freshness
        self.expiry=expiry
    def details(self):
        print("THE DETAILS OF THE SNACKS: ",self.name,self.price,self.quantity,self.freshness,self.expiry)
class Customer:
    def __init__(self,name,phoneno,password):
        self.name=name
        self.phoneno=phoneno
        self.password=password


class Registration:
    @staticmethod
    def register(name,phoneno,password,user_lists):
        for i in user_lists:
            if(i.name==name and i.phoneno==phoneno):
                print("THIS MOBILE NUMBER ALREADY EXISTS \nPLEASE LOGIN")
                return 
        user=Customer(name,phoneno,password)
        user_lists.append(user)
        print("SUCCESSFULLY REGISTERED")
        return user
    @staticmethod 
    def login(phoneno,password,user_lists):
        for i in user_lists:
            if(i.phoneno==phoneno):
                break
        else:
            print("DO REGISTER")
            return 
        print("SUCCESSFULLY LOGGED IN")
        return i 
app=GroceryApp()
app.start()





