# hackerRank soru 1
##  Dizideki negatif pozitif ve sıfır eleman addedini toplam eleman addedine bölüp sıfırdan sonra altı basamaklı bir sayı olarak yazdırma

``` javaScript
    
    
    let arr = [1, 2, 3, -1, -2, -3, 0, 0];
 
        function plusMinus(arr) {

            var sifirSayac = 0;
            var pozitifSayac = 0;
            var negatifSayac = 0;

            arr.map(function (sayi) {
                if (sayi == 0) {
                    sifirSayac++;
                } else if (sayi > 0) {
                    pozitifSayac++;
                } else {
                    negatifSayac++;
                }
            });

            var toplam = sifirSayac + negatifSayac + pozitifSayac;
            console.log(toplam);

            let pozitifOran = (pozitifSayac / toplam).toFixed(6);
            let sifirOran = (sifirSayac / toplam).toFixed(6);
            let negatifOran = (negatifSayac / toplam).toFixed(6);

            console.log(pozitifOran);
            console.log(negatifOran);
            console.log(sifirOran);
        }

        plusMinus(arr);
```

## output
0.375000 <br />
0.375000  <br />
0.250000 <br />

# hackerRank soru 2
##  dizideki elemanlarının toplamının en küçük değeri ve en büyük değeri

``` javascript

 var arr = [154,2,43,84,25];

        function miniMaxSum(arr) {
            
            arr.sort(function(a, b){return a - b});
            console.log(arr);
            
            var maxToplam = 0;
            for(let i =1 ; i <arr.length ; i++){
                maxToplam+= arr[i];
               
            }
            console.log(maxToplam);

            var minToplam = 0;
            for(let i =0 ; i <arr.length-1 ; i++){
                minToplam+= arr[i];
               
            }
            console.log(minToplam);

        }

        miniMaxSum(arr);
```

## output
306 <br />
154  <br />

# hackerRank soru 3
##  12 lik saat sistemini AM VE PM dikkate edilerek 24 lük saat sistemine (military) çevirme

``` javascript

 let s = "04:59:59PM";

        function timeConversion(s){
            
            let diziTamSaat = s.split(":");
            let saat=Number(diziTamSaat[0]);
            let dakika=diziTamSaat[1];
            let saniye=diziTamSaat[2];
            var amPm = (saniye.toString()).slice(2);
            saniye=(saniye.toString()).slice(0,2);
            

            if(saat==12 && amPm=="AM"){
                saat=0;
                let militaryFormat=`${"0"+saat.toString()}:${dakika}:${saniye}`;
                return militaryFormat;
            }
            else if(saat<12 && amPm==="PM"){
                saat = saat + 12 ;
                let militaryFormat=`${saat.toString()}:${dakika}:${saniye}`;
                return militaryFormat;
            }
            else{
                if(saat<10){
                    saat = "0"+saat;
                }
                let militaryFormat=`${saat.toString()}:${dakika}:${saniye}`;
                return militaryFormat;
            }
        }
```

## output 
16:59:59 <br />

# hackerRank soru 4
##  score göre rekor bulma

``` javascript
 var scores = [12, 24, 10, 24]

        function breakingRecords(scores) {
            let min = scores[0],
                max = scores[0],
                countMin = 0,
                countMax = 0;
            for (const element of scores) {
                if (element < min) {
                    min = element;
                    countMin++;
                }
                if (element > max) {
                    max = element;
                    countMax++;
                }
            }
            return [countMax, countMin];
        }
```

## output 
1 1 <br />

# hackerRank soru 6
## Bir dizide i<j koşuluyla ve verilen k sayısına i ve j inci elemnanın toplamının tam bölünmesini sağlayan ikili sayısı

``` javascript

        var n = 5;
        var k = 3;
        var ar = [2, 8, 6 ,8, 4];

        function divisibleSumPairs(n, k, ar) {
            var sayac = 0;
            for (var i = 0; i <= n; i++) {
                for (var j = 0; j <= n; j++) {

                    if ((i < j) && (ar[j] + ar[i]) % k == 0) {
                        console.log(ar[i], ar[j]);
                        sayac++;
                    }
                }
            }
            return sayac;
        }
        console.log(divisibleSumPairs(n, k, ar));

```

## output 
2 4 <br />
8 4 <br />
8 4 <br />
3 <br />

# hackerRank Mock 1
## ELemanların medyanını hesaplama

``` javascript

       var arr = [0, 1, 2, 3, 4, 5, 6, 7]

        function findMedian(arr) {

            // Write your code here
            var siralaDizi = arr.sort();
            var diziUzunluk = siralaDizi.length;
            if (diziUzunluk % 2 == 1) {
                let ortaEleman = Math.floor(diziUzunluk / 2);
                let medyan = siralaDizi[ortaEleman];
                return medyan;
            } else {
                let ortaEleman2 = diziUzunluk / 2;
                let medyan2 = (siralaDizi[ortaEleman2 - 1] + siralaDizi[ortaEleman2]) / 2
                return medyan2;
            }
        }
        console.log(findMedian(arr));

```

## output 
3.5 <br />

# hackerRank soru 7
## Dizideki tekrarlanmayan benzersiz elemanı bulma

``` javascript

       const a = [84 ,48, 13 ,20, 61, 20, 33, 97 ,34, 45 ,6, 63, 71, 66, 24, 57 ,92, 74, 6, 25, 51 ,86, 48 ,15 ,64, 55, 77, 30, 56 ,53 ,37 ,99, 9, 59, 57, 61 ,30 ,97                       ,50, 63, 59, 62, 39, 32, 34, 4 ,96, 51, 8 ,86 ,10, 62, 16, 55, 81, 88 ,71 ,25 ,27 ,78, 79, 88, 92, 50, 16, 8, 67, 82, 67, 37, 84, 3, 33 ,4 ,78, 98                      ,39, 64, 98, 94, 24, 82, 45, 3, 53 ,74 ,96, 9, 10, 94 ,13, 79 ,15, 27, 56 ,66 ,32, 81, 77];
        
        function lonelyinteger(a) {
            const siralidizi = a.sort(function(a,b){return a-b});
            console.log(siralidizi);
           
            for (var i = 0; i <=100 ; i++) {
              
                var uzunlukDizi = siralidizi.length;
                if(uzunlukDizi == 1 ){
                    return "sonuc" , siralidizi[0];                
                }
                
                var eleman = siralidizi.shift();
               
                console.log("eleman 1.kez çıkarılıdı: ", eleman)
                
                var varMi = siralidizi.includes(eleman);

                console.log("eleman: ", eleman);
                console.log("dizinin ilk hali", siralidizi);
                if(!varMi){
                    return eleman;
                }
                else if (varMi) {
                    siralidizi.shift();
                    var uzunlukDizi2 = siralidizi.length;
                    console.log("eleman 2.kez çıkarılıdı: ", eleman)
                    console.log("dizinin son hali", siralidizi);
                    console.log("uzunluk ", uzunlukDizi2);
                }
                else{
                    return  "sonuc3: ", siralidizi[0];
                }
                if(uzunlukDizi2 == 1 ){
                    return "sonuc2: ", siralidizi[0];
                }

            }
        }
       console.log(lonelyinteger(a));

```

## output 
99 <br />

# hackerRank soru 8
## öğrenci notlarından 38 den küçük olanı yuvarlama , eğer not ile 5'in bir sonraki katı arasındaki fark 3 ten küçükse notları 5'in bir sonraki katına yuvarlama

``` javascript

        var grades = [73, 67, 38, 33,48,34,98];
        function gradingStudents(grades) {
            var dizi = [];
            for (var i = 0; i < grades.length; i++) {

                if (grades[i] < 38) {
                    dizi.push(grades[i]);
                } else if ((grades[i] + 1) % 5 ==0) {
                    dizi.push(grades[i]+1);
                 
                } else if ((grades[i] + 2) % 5 == 0) {
                    dizi.push(grades[i]+2);
                    
                } else {
                    dizi.push(grades[i]);
                    
                }         
            }
            return dizi;
        }
        console.log(gradingStudents(grades));

```

## output 
 [75, 67, 40, 33, 50, 34, 100] <br />
 
 # hackerRank soru 9
## 10 luk tabandaki sayıyı (decimal) 2 lik tabana çevirme daha sonra 0 ları 1 ile , 1 leri 0 ile yer değiştirdikten sonra 2 lik tabandaki sayıyı 10 luk tabana çevirme

``` javascript

        var n = 78;
        function flippingBits(n) {

            var dizi = [];
            var sayi = 0;
            for (;;) {

                var modAl = n % 2;
                console.log(modAl);
                if (modAl == 1) {
                    dizi.unshift(0);
                } else if (modAl == 0) {
                    dizi.unshift(1);
                }

                var diziUzunluk = dizi.length;
                n = Math.floor(n / 2);
                if (n < 1)
                    break;
            }
            console.log("uzun", diziUzunluk);
            for (var i = 0; i <= 32 - (diziUzunluk + 1); i++) {
                dizi.unshift(1);
            }
            
            for (var i = 0; i < 32; i++) {
                sayi = sayi + (dizi[i] * Math.pow(2, (31 - i)));             
            }
            return sayi;
            
         
       }
       
       console.log(flippingBits(n));

```

## output 
 4294967217 <br />
 
  # hackerRank soru 10
## kare matrisin köşegenler farkının mutlak değerce değerini hesaplama 

``` javascript

         var arr = [
            [1, 2, 3 ,4],
            [5, 6, 7 ,8],
            [9, 7, 2 ,1],
            [6, 5, 4 ,3],
        ]

        function diagonalDifference(arr) {
            var diziUzunluk = arr.length;
            console.log(diziUzunluk);

            var solKose = 0;
            var sagKose = 0;
            var sonuc ;

            for (var i = 0; i <= diziUzunluk; i++) {

                for (var j = 0; j < diziUzunluk; j++) {

                    if (i == j) {
                        console.log("sol eleman: ",arr[i][j]);
                        solKose += arr[i][j];
                        console.log("sol", solKose);

                    }
                    if ((i + j) == diziUzunluk-1) {
                        console.log("sağ eleman: ",arr[i][j]);
                        sagKose += arr[i][j];
                        console.log("sağ", sagKose);
                    }
                }
                
            }
            sonuc = Math.abs(solKose-sagKose);
            console.log(sonuc);

        }
        diagonalDifference(arr)

```

## output 
12 <br />

# hackerRank soru 11
## string ifadenin ingiliz alfabesindeki 26 harfi içermesi durumunda pangram bir tanesini bile içermemesi durumunda not pangram döndürülür

``` javascript

         var s ="We promptly judged antique ivory buckles for the  prize";
        function pangrams(s) {
            // Write your code here
            var kucukHarf = s.toLowerCase();
            var boslukAl = kucukHarf.replaceAll(" ","");
            console.log(boslukAl);
            var dizi = boslukAl.split("");
            console.log(dizi);
            var alphabaet = ["a","b","c","d","e","f","g","h","i","j","k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z"];
            
            var sonuc = alphabaet.every(function(harf){
                return dizi.includes(harf);
            })
            if(sonuc){
                return "pangram"
            }
            else{
                return "not pangram"
            }
            

        }
        console.log(pangrams(s));

```

## output 
not pangram <br />
