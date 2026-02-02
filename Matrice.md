# Glavna dijagonala 
### i == j
<br>

vizualno:
```java
X . . .
. X . .
. . X .
. . . X
```
kod:
```java
for(int i = 0; i < n; i++){
    suma += A[i][i];
}
```
---

# Sporedna dijagonala
### i + j == n - 1
<br>

vizualno:
```java
. . . X
. . X .
. X . .
X . . .
```
kod:
```java
for(int i = 0; i < n; i++){
    suma += A[i][n - 1 - i];
}
```
---

# Iznad glavne dijagonale
### j > i
<br>

vizualno:
```java
X * * *
. X * *
. . X *
. . . X
```
kod:
```java
for(int i = 0; i < n; i++){
    for(int j = i + 1; j < n; j++){
        suma += A[i][j];
    }
}
```
---
# Ispod glavne dijagonale
### j < i
<br>
vizualno:

```java
X . . .
* X . .
* * X .
* * * X
```

kod:
```java
for(int i = 0; i < n; i++){
    for(int j = 0; j < i; j++){
        suma += A[i][j];
    }
}

```
---
# Prvi red
### i == 0
<br>


kod:
```java
for(int j = 0; j < n; j++){
    suma += A[0][j];
}
```
---
# Prvi stupac
### j == 0

<br>

kod:
```java
for(int i = 0; i < n; i++){
    suma += A[i][0];
}


```
---
# Zmijski ispis
### Paran red se ispisuje normalno, neparan obrnuto.
<br>

```java
for(int i = 0; i < n; i++){
    if(i % 2 == 0){
        for(int j = 0; j < m; j++){
            System.out.print(A[i][j] + " ");
        }
    } else {
        for(int j = m - 1; j >= 0; j--){
            System.out.print(A[i][j] + " ");
        }
    }
    System.out.println();
}

```
---
