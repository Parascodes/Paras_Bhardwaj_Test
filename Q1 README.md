def line_overlap():
    a = int(input('Please enter starting point of first line : '))
    b = int(input('Please enter ending point of first line : '))
    p = int(input('Please enter starting point of second line : '))
    q = int(input('Please enter ending point of second line : '))
    if a>b:  # If input is given in for ex- 4,1 format and not 1,4 then to change it to 1,4 format so as to count the range
        a = a+b
        b = a-b
        a = a-b
    if p>q:
        p = p+q
        q = p-q
        p = p-q
    l1 = []
    l2 = []
    flag = 0
    for i in range(a,b+1): # The logic is that if any 2 line segment on x axis overlap then it must have at least one point in common between those two lines
        l1.append(i)
    for j in range(p,q+1):
        l2.append(j)
    for var1 in l1:
        if flag == 1:
            break
        for var2 in l2:
            if var1 == var2:
                flag = 1
                break
            else:
                flag = 0
                continue
   
    if flag == 1 :
        return('Both lines overlap')
    else :
        return('No overlap between the lines')
