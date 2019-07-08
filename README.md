total = 256
def distinct(string, n):
    count = [0]
    count=count* total
    for i in range(n): 
        count[ord(string[i])] += 1
    maxi = 0
    for i in range(total): 
        if (count[i] != 0): 
            maxi += 1    
    return maxi 
  
def substring_length(string):
    n = len(string)
    maxi = distinct(string, n) 
    minl = n     
    for i in range(n): 
        for j in range(n): 
            s = string[i:j] 
            s_length = len(s) 
            substring_distinct = distinct(s,s_length) 
            if (s_length < minl and maxi == substring_distinct):
                minl = s_length
    return minl 
string = input()
li = substring_length(string); 
print(li) 
  

