
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

# Adding Search and Pagination

useSearchParams  : Mevcut URL'nin parametrelerine erişir. Örneğin, /dashboard/invoices?page=1&query=pending böyle bir url'nin parametreleri böyle görünür ==> {page: '1', query: 'pending'}

usePathName : Bu hook ile mevcut URL'nin parametrelerini okuruz. Örneğin /dashboard/invoices gibi bir URL'de usePathName kullanırsak return olarak '/dashboard/invoices'

useRouter : Bizi bir başka pageye yönlendirmeyi sağlayan bir hooktur. Örneğin 

const route = useRouter()

route('/main-page')

# Kullanım 

useSearchParams' ı kullanmak için URLSearchParams adlı bir Web API kullanılır. Bu web API URL'nin query parametrelerini manipule etmemizi sağlar.

useRouter hookunun replace metodu ile mevcut url yerine sağlanılan url kısmına navigate ederiz page'i

Örneğin var olan bir url'i paylaşıyoruz ve bu URL'nin otomatik olarak inputa aktarılmasını istiyorsak inputtaki default value özelliğini kullanmamız gerekiyor. Örneğin : 

  defaultValue={searchParams.get('query')?.toString()}


## searchParams props && useSearchParams()

Eğer client side tarafında çalışıyorsak useSearchParams, eğer server side tarafında isek searchParams props'unu kullanırız!

# Debouncing 

Search kısmına sürekli keystroke yaptığımızda database kısmına ardı ardına istekler gerçekleştiririz. Bunun önüne geçmek için debouncing kullanılır.
import { useDebouncedCallback } from 'use-debounce';

const handleSearch = useDebouncedCallback((term) => {
},300)

Her 0.3 saniyede userin girdiyi bırakıp bırakmadığını kontrol eder.

## Mutating Data

Server aksiyonları next.js içerisinde cache olayları ile bağlantılıdır! Yani api ara isteklerini ortadan kaldırır ve direkt server ile iletişime geçer.

Server component'lerin içerisinde bulunan formların action kısmına action fonksiyonları yerleştirilir. Ve gerekli fonksiyonun logici yazılır. Yani server actions bir post isteği oluşturur. Yani ekstradan bir api isteği yazmamıza gerek yoktur.