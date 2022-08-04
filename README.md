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
0.250000
