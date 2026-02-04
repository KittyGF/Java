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

```java
	
	public static int[][] trans (int A[][], int n, int m){
	    int B [] [] = new int[m][n];
	    for(int i=0; i<n; i++){
	        for(int j=0; j<m; j++){
	            B[j][i]=A[i][j];
	        }
	    }
	    return B;
	}
```
---


# Faktorijel
<br>

```java
    public static int faktorijel(int unos){
        int fakt = 1;
        for(int i=1; i<=unos; i++){
            fakt*=i;
        }
            return fakt;
    }

```
---


# Potencija
<br>

```java
    public static int potencija(int a, int b){
        int rezultat = 1;
        for(int i=1; i<=b; i++){
            rezultat *=a;
        }
        return rezultat;
    }
```
---

# Aritmeticka sredina sporedne dijagonale
<br>

```java
for(int i=0; i<a; i++){
    suma+=matrica[i][a-i-1];
}
double ars = suma/a;
System.out.println("Aritmeticka sredina sporedne dijagonale je: " + ars);
```
---

# Suma neparnih elemenata prvog retka 
<br>

```java
int sumaReda = 0;
int sumaStupca = 0;
for(int i=0; i<a; i++){
    if(matrica [0][i] %2 != 0){
        sumaReda+=matrica[0][i];
        }
    }
System.out.println("Suma neparnih elemenata prvog retka je: " +sumaReda);
```
---

# Suma neparnih elemenata prvog stupca 
<br>

```java
for(int i=0; i<a; i++){
    if(matrica[i][0]%2 != 0){
        sumaStupca+=matrica[i][0];
        }
    }
System.out.println("Suma neparnih elemenata prvog stupca je: " +sumaStupca);
```
---

#  Elemenati iznad i ispod sporedne dijagonale
<br>

```java
  public static int funkcija(int A[][], int n){
      int suma2 = 0;
      int suma3 = 0;
      //elementi iznad i ispod sporedne dijagonale
      for(int i=0; i<n; i++){
          for(int j=0; j<n; j++){
              if(j < n - i - 1){
                  suma2 += A[i][j];
              }else if(j > n - i - 1){
                  suma3 += A[i][j];
              }
          }
      }
```
---

# Koliko ima pojavljivanja broja 0, a da su oko njega sve jedinice.
<br>

```java
    public static int brojPojavljivanja(int A [][], int n){
        int brojac=0;
        for(int i=1; i<n-1; i++){
            for(int j=1; j<n-1; j++){
                if(A[i][j] == 0 && A[i-1][j] == 1 && A[i+1][j] == 1 && A[i][j-1] == 1 && A[i][j+1] == 1){
                    brojac++;
                }
            }
        }
        return brojac;
    }

```
---

