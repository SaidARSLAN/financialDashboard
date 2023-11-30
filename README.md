
## Klasörler

/app : Bütün routeleri,componentleri ve mantıkları barındıran dosyadır.

/app/lib : data fetching işlemleri ve reusable utilitiesler buradadır.

/app/ui : Bütün UI buradadır. Örneğin kartlar,tablolar ve formlar.

/public : statik dosyaların barındığı alandır.

/scripts : Veritabanı işlemlerinin gerçekleştiği kısım burasıdır.

## Fontlar 

Kendi fontunu eklemek için şu şekilde yap

import { Inter } from 'next/font/google';

import { Lusitana } from 'next/font/google';

export const inter = Inter({ subsets: ['latin'] });

export  const lusitana = Lusitana({ subsets: ['latin'], weight:["400","700"]});


## Resimler

Image import etmek için geleneksel yol yerine <Image /> adlı komponenti kullanırız.
Özellikleri next.js ana sayfasında yazmaktadır!

## Layout Oluşturma ve Sayfalar

Sadece page componentleri update olur layout render olmazken.

Bir tane root layout olmak zorunda App klasörünün altında!


# Suspense Component

Loadinglerde componentlerin gecikenlerin birbiri ardına gelmesini sağlar!