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

# Zbrajanje
### sum += A[i][j];
<br>

```java
int sum = 0;
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        if(condition) {
            sum += A[i][j];
        }
    }
}
System.out.println(sum);


```
---

# Metode
<br>

```java
public static int myFunction(int[][] A, int n) {
    int sum = 0;
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < n; j++) {
            // logic
        }
    }
    return sum;
}


```
---

# Try-catch
<br>

```java
int x = 0;
Scanner input = new Scanner(System.in);

while(true) {
    try {
        x = input.nextInt();
        break;
    } catch(Exception e) {
        System.out.println("Enter a number!");
        input.nextLine(); // clear bad input
    }
}



```
---

# Threads and join
<br>

```java
class MyThread implements Runnable {
    int[] row;

    MyThread(int[] row) {
        this.row = row;
    }

    public void run() {
        int sum = 0;
        for(int x : row) sum += x;
        System.out.println(sum);
    }
}

```

```java
Thread t = new Thread(new MyThread(A[i]));
t.start();
t.join();

```
---

# Transponirana matrica
<br>

```java
for(int i = 0; i < n; i++) {
    for(int j = 0; j < m; j++) {
        B[j][i] = A[i][j];
    }
}

```
---

