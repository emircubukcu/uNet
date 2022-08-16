# unet-tensorflow-labelme

## LabelMe
LabelMe resim üzerinde çokgenler ile istediğiniz öğeleri etiketlemenize yarayan bir uygulamadır.Burdaki linkten[https://github.com/wkentaro/labelme/releases] kendi bilgisayarınıza uygun olan versiyonu seçip indirin.

İndirme işleminden sonra kullanacağınız resimlerin bulunduğu klasörü seçip sırasıyla istediğiniz bölgeyi seçip etiketleyiniz.


## Kurulum
Eğer kendi bilgisayarınızda çalıştırmak istemiyorsanız tüm dosyaları Google Drive klasörüne yerleştirip kullanabilirsiniz.


**macOS** kullanıyorsanız , kuruluma başlamadan önce aşağıdaki komutu çalıştırın.

```sh
❯ brew install pyqt
```

Unet için gerekli herşey requirements.txt dosyasında belirtilmiştir. Tüm sistemi kurabilmek için öncelikle Anaconda kurmanız gerekmektedir.  
Anaconda kurulumu bittikten sonra aşağıdaki komutu çalıştırın.

```sh
❯ conda create -n unet -y python=3.9 && conda activate unet && pip install -r requirements.txt
```

## Veri Seti 

### VOC formatında veri oluşturma

Labelme kullanarak oluşturduğunuz veriyi `datasets/train` yoluna kaydetin, ve verinizdeki etiketleri alt alta yazdığınız bir bir dosya oluşturup  `datasets/labels.txt` konumuna kaydetin.


`datasets/train` klasöründen voc datasını oluşturmak için aşağıdaki komutu çalıştırın.

```sh
❯ make voc
```

>Eğer yeni bir voc verisi oluşturup ilk verinin üzerine yazmak istiyorsanız aşağıdaki komutu çalıştırın.
>
> ```sh
> ❯ make re-voc
> ```

## Eğitim ve Test

`sample.ipynb` adlı dosyayı açın ve gerekli bölümleri çalıştırın.Tüm çalışma süresi bittiğinde eğitilmiş model `logs/the-last-model.h5` şeklinde kaydedilecek.

Eğer `datasets/test` klasörüne koyduğunuz bir resimi `sample.ipynb` dosyasındaki test bölümünde doğru bir şekilde belirttiyseniz otomatik bir şekilde testi gerçekleştirip sonucu geri döndürecektir.



