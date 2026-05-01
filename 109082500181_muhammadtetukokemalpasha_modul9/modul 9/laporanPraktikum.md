# <h1 align="center">Laporan Praktikum Modul 5 - ... </h1>
<p align="center">[Muhammadtetukokemalpasha] - [109082500181]</p>

## Unguided 

### 1. [Soal]
#### soal1.go

```go
package main

import (
	"fmt"
	"math"
)

type titik struct {
	x,y int
}

type lingkaran struct {
	pusat  titik
	radius int
}

func jarak(p, q titik) float64 {
	dx := float64(p.x - q.x)
	dy := float64(p.y - q.y)
	return math.Sqrt(dx*dx + dy*dy)
}

func didalam(c lingkaran, p titik) bool {
	return jarak(c.pusat, p) <= float64(c.radius)
}

func main() {
	var c1, c2 lingkaran
	var p titik

	fmt.Scan(&c1.pusat.x, &c1.pusat.y, &c1.radius)
	fmt.Scan(&c2.pusat.x, &c2.pusat.y, &c2.radius)
	fmt.Scan(&p.x, &p.y)

	inC1 := didalam(c1, p)
	inC2 := didalam(c2, p)

	if inC1 && inC2 {
		fmt.Println("Titik di dalam lingkaran 1 dan 2")
	} else if inC1 {
		fmt.Println("Titik di dalam lingkaran 1")
	} else if inC2 {
		fmt.Println("Titik di dalam lingkaran 2")
	} else {
		fmt.Println("Titik di luar lingkaran 1 dan 2")
	}
}

```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_1](https://github.com/tetukopasha-tech/109082500181_muhammadtetukokemalpasha_modul9/blob/main/109082500181_muhammadtetukokemalpasha_modul9/modul%209/output/SOAL1.png)
[Penjelasan: Program ini mengimplementasikan konsep geometri menggunakan struct untuk menentukan posisi sebuah titik terhadap dua buah lingkaran dengan menghitung jarak Euclidean antara titik pusat lingkaran dan titik koordinat yang diinputkan.]

### 2. [Soal]
#### soal2.go

```go
package main

import (
	"fmt"
	"math"
)

func masukanarray(n int, arr []int) {
	for i := 0; i < n; i++ {
		fmt.Printf("Masukkan elemen indeks ke-%d: ", i)
		fmt.Scan(&arr[i])
	}
}

func main() {
	var n int
	fmt.Print("Masukkan jumlah elemen nilai: ")
	fmt.Scan(&n)
	arr := make([]int, n)
	masukanarray(n, arr)

	fmt.Println("a. Keseluruhan isi array: ")
	for _, val := range arr {
		fmt.Print(val, " ")
	}
	fmt.Println()

	fmt.Println("b. Elemen dengan indeks ganjil: ")
	for _, vel := range arr {
		if vel%2 != 0 {
			fmt.Print(vel, " ")
		}
	}
	fmt.Println()

	fmt.Println("c. Elemen dengan indeks genap: ")
	for _, vel := range arr {
		if vel%2 == 0 {
			fmt.Print(vel, " ")
		}
	}
	fmt.Println()

	var x int
	fmt.Print("Masukkan bilangan x untuk indeks kelipatan: ")
	fmt.Scan(&x)
	fmt.Printf("d. Elemen dengan indeks kelipatan %d: ", x)
	for i := 0; i < len(arr); i++ {
		if x != 0 && i%x == 0 {
			fmt.Print(arr[i], " ")
		}
	}
	fmt.Println()

	var deleteIdx int
	fmt.Print("Masukkan indeks elemen yang ingin dihapus: ")
	fmt.Scan(&deleteIdx)
	arr = append(arr[:deleteIdx], arr[deleteIdx+1:]...)
	fmt.Print("e. Keseluruhan isi array setelah dihapus: ")
	for _, val := range arr {
		fmt.Print(val, " ")
	}
	fmt.Println()

	var sum float64
	for _, val := range arr {
		sum += float64(val)
	}
	var average float64
	if len(arr) > 0 {
		average = sum / float64(len(arr))
	}
	fmt.Printf("f. Rata-rata dari bilangan di dalam array: %.2f\n", average)

	var varianceSum float64
	for _, val := range arr {
		varianceSum += math.Pow(float64(val)-average, 2)
	}
	var stdDev float64
	if len(arr) > 0 {
		stdDev = math.Sqrt(varianceSum / float64(len(arr)))
	}
	fmt.Printf("g. Standar deviasi (simpangan baku): %.2f\n", stdDev)
}
```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_2](https://github.com/tetukopasha-tech/109082500181_muhammadtetukokemalpasha_modul9/blob/main/109082500181_muhammadtetukokemalpasha_modul9/modul%209/output/SOAL2.png)
[Penjelasan: Program ini mendemonstrasikan manipulasi array yang komprehensif, mulai dari menampilkan elemen berdasarkan indeks ganjil, genap, atau kelipatan tertentu, hingga melakukan penghapusan elemen dan penghitungan statistik berupa rata-rata serta standar deviasi.]

### 3. [Soal]
#### soal3.go

```go
package main

import (
	"fmt"
)

func main() {
	var A,B string
	var klubA, klubB []int
	fmt.Print("maskan klub A:")
	fmt.Scan(&A)
	fmt.Print("maskan klub B:")
	fmt.Scan(&B)
	var scoreA, scoreB int = 1, 1
	var i int = 1
	for scoreA > -1 && scoreB > -1{
		fmt.Print("pertandingan ke ",i,":")
		fmt.Scan(&scoreA,&scoreB)
		klubA = append(klubA,scoreA)
		klubB = append(klubB,scoreB)
		i++
	}
	var j int = 1
	for i := 0 ; i < len(klubA); i++ {
		if klubA[i]>klubB[i]{
			fmt.Println("hasil",j,":",A)
		}else if klubA[i]<klubB[i]{
			fmt.Println("hasil",j,":",B)
		}else{
			fmt.Println("hasil",j,"draw")
		}
		j++
	}
}
```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_2](https://github.com/tetukopasha-tech/109082500181_muhammadtetukokemalpasha_modul9/blob/main/109082500181_muhammadtetukokemalpasha_modul9/modul%209/output/SOAL3.png)
[Penjelasan: Program ini berfungsi sebagai pencatat skor pertandingan antara dua klub yang menggunakan perulangan tak terbatas hingga pengguna memasukkan angka negatif sebagai penanda berhenti (sentinel), sembari secara otomatis menentukan pemenang atau hasil imbang di setiap sesi.]

### 4. [Soal]
#### soal3.go

```go
package main

import "fmt"

const max int = 127

type tabel [max]rune

func main() {
	var m int
	var tab tabel
	input(&tab, &m)
	t := balikanArr(&tab, &m)
	cetakArr(t)
	fmt.Println(palidrom(tab,t))
}

func input(t *tabel, n *int) {
	var input string
	for *n < max {
		fmt.Scan(&input)
		char := rune(input[0])
		if char == '.' {
			break
		}
		t[*n] = char
		(*n)++
	}
}

func cetakArr(t tabel) {
	for _,vel := range t{
		fmt.Printf("%c",vel)
	}
	fmt.Println()
}

func balikanArr(t *tabel, n *int)tabel{
	var balik tabel
	var j int 
	for i := *n - 1; i >= 0; i-- {
		char := (*t)[i]
		balik[j] = char
		j++
	}
	return balik 
}

func palidrom(t tabel, T tabel)bool {
	if t == T {
		return true
	}else{
		return false
	}
}

```
### Output Unguided :

##### Output 
![Screenshot Output Unguided 1_2](https://github.com/tetukopasha-tech/109082500181_muhammadtetukokemalpasha_modul9/blob/main/109082500181_muhammadtetukokemalpasha_modul9/modul%209/output/SOAL4.png)
[Penjelasan: Program ini menggunakan logika pemrosesan karakter untuk memvalidasi sebuah kata sebagai palindrom dengan cara membandingkan isi array asli dengan hasil pembalikannya (reverse) melalui fungsi khusus guna menghasilkan nilai kebenaran berupa boolean.]

