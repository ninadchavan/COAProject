# Floating Point Arithmetic

def convert():
    number = input("Enter number: ")
    number = list(number)
    sign = int(number[0])
    exp = number[1:9]
    signifi = number[9:]
    exponent = 0
    for i in range(7,-1,-1):
        if(exp[i] == '1'):
            exponent += 2**(7-i)
    exponent = exponent - 127
    significand = 1
    for i in range(0, 23):
        if(signifi[i] == '1'):
           significand += 2**(-(i+1)) 
            
    num = (-1)**(sign) * significand * (2**exponent)
    return num    

def sum(x, y):
    print("Sum = {0}".format(x+y))

def diff(x, y):
    print("Difference = {0}".format(x-y))
    
x = convert()
y = convert()

print("X = {0}".format(x))
print("Y = {0}".format(y))

sum(x, y)
diff(x, y)