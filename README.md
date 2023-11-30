
## Klasörler

/app : Bütün routeleri,componentleri ve mantıkları barındıran dosyadır.

/app/lib : data fetching işlemleri ve reusable utilitiesler buradadır.

/app/ui : Bütün UI buradadır. Örneğin kartlar,tablolar ve formlar.

/public : statik dosyaların barındığı alandır.

/scripts : Veritabanı işlemlerinin gerçekleştiği kısım burasıdır.(daha detaylı öğrenilip açıklanılacak!)

## Fontlar 

Kendi fontunu eklemek için şu şekilde yap

import { Inter } from 'next/font/google';

import { Lusitana } from 'next/font/google';

export const inter = Inter({ subsets: ['latin'] });

export  const lusitana = Lusitana({ subsets: ['latin'], weight:["400","700"]});


## Resimler

Image import etmek için geleneksel yol yerine <Image /> adlı komponenti kullanırız.
