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

