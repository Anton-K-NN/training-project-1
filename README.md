# training-project-1
Решение учебных задач курса Stepik.org "Программирование на Python".

Выведите таблицу размером n×n, заполненную числами от 1 до n2 по спирали, выходящей из левого верхнего угла и закрученной по часовой стрелке, как показано в примере (здесь n=5):

Sample Input:

5
Sample Output:

1 2 3 4 5
16 17 18 19 6
15 24 25 20 7
14 23 22 21 8
13 12 11 10 9

n=int(input())
m=n
a=[[0 for i in range(n)]for j in range(n)]
s,i,j,x,y=1,0,0,0,0
while s<=m*m:
    #вправо по верхней строке
    while j<=n-1:
        a[i][j]=s
        s+=1
        j+=1
    i+=1
    j=n-1

    #вниз по правому столбцу
    while i<=n-1:
        a[i][j]=s
        s+=1
        i+=1

    #влево по нижней строке
    i-=1
    j-=1
    while j>=x:
        a[i][j]=s
        s+=1
        j-=1

    #вверх по левому стобцу
    i-=1
    j+=1
    while i>y:
        a[i][j]=s
        s+=1
        i-=1
    print (j)
    j+=1
    i+=1
    x+=1
    y+=1
    n-=1

for  i in range(0,m):
    for j in range(0,m):
        print(a[i][j], end=' ')
    print()

