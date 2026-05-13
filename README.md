# Defaultv2 - tahribat.com Tema Şablonu

tahribat.com için kullanıcı tarafından özelleştirilebilir CSS tema şablonu. Fork'layıp kendi temanızı oluşturun.

## Özellikler

- Otomatik karanlık mod (işletim sistemi tercihine göre)
- 70+ CSS değişkeni ile kolay renk özelleştirmesi
- Duyarlı tasarım (masaüstü, tablet, mobil)
- Yazıcı dostu baskı stilleri
- Build sistemi veya JavaScript gerektirmez

## Dosyalar

| Dosya              | Kapsam                                                                    |
| ------------------ | ------------------------------------------------------------------------- |
| `main.css`         | Genel stiller, tasarım değişkenleri, karanlık mod, formlar, tablolar, yorumlar, sayfalama |
| `DefaultPage.css`  | 3 sütunlu sayfa düzeni, duyarlı daraltma                                 |
| `ForumView.css`    | Forum gönderi görünümü, avatar paneli, alıntı blokları                   |
| `tbtmenu2.css`     | Üst navigasyon menüsü, mobil hamburger menüsü                            |
| `stylus-inject.css`| 4 CSS dosyasının birleşmiş hali (test için)                              |

## Kurulum

1. Bu repoyu fork'layın
2. CSS dosyalarını düzenleyin
3. tahribat.com tema ayarlarından dosyalarınızı yükleyin

## Karanlık Mod

Karanlık mod, işletim sistemi veya tarayıcı `prefers-color-scheme: dark` tercih ettiğinde otomatik olarak aktif olur. Manuel geçiş butonu yoktur.

Tüm renkler `:root` içindeki CSS değişkenleri üzerinden yönetilir:

```css
:root {
  --color-bg-page: #ecf0f1;      /* Açık mod */
  --color-text-primary: #333333;
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-bg-page: #121212;     /* Karanlık mod */
    --color-text-primary: #e0e0e0;
  }
}
```

Renkleri değiştirmek için `:root` bloklarındaki değişkenleri düzenleyin.

## Duyarlı Tasarım

| Kırılma Noktası | Davranış                                        |
| --------------- | ----------------------------------------------- |
| >980px          | 3 sütunlu masaüstü düzeni                       |
| 980px           | 2 sütun yan yana, orta alan tam genişlik        |
| 600px           | Tek sütun düzeni                                |
| 480px           | Yan panel gizlenir, hamburger menü aktif olur   |

## Özelleştirme

### Renk Değiştirme

`main.css` dosyasındaki `:root` bloklarında CSS değişkenlerini düzenleyin. Her değişkenin açık ve karanlık mod değeri vardır.

Örnek renk değişkenleri:

| Değişken                  | Açıklama           |
| ------------------------- | ------------------ |
| `--color-bg-page`         | Sayfa arka planı   |
| `--color-bg-surface`      | Kart arka planları |
| `--color-text-primary`    | Ana metin rengi    |
| `--color-link`            | Bağlantı rengi     |
| `--color-nav-bg`          | Menü arka planı    |
| `--color-border`          | Genel çerçeve      |

### Yeni Stil Ekleme

- Genel stiller: `main.css`
- Sayfa düzeni: `DefaultPage.css`
- Forum gönderi stilleri: `ForumView.css`
- Navigasyon menüsü: `tbtmenu2.css`

## Yerel Test

Değişikliklerinizi canlı sitede test etmek için:

1. Tüm dosyaları birleştirin:
   ```bash
   cat main.css DefaultPage.css ForumView.css tbtmenu2.css > stylus-inject.css
   ```
2. [Stylus](https://github.com/openstyles/stylus) tarayıcı eklentisini kurun
3. tahribat.com için yeni bir stil oluşturup `stylus-inject.css` içeriğini yapıştırın
4. Sayfayı yenileyerek değişiklikleri görün

## Teknik Notlar

- Build adımı yoktur. CSS dosyalarını doğrudan düzenleyin.
- Platform HTML yapısını değiştiremezsiniz, yalnızca CSS düzenlenebilir.
- Float tabanlı duyarlı düzeni kullanılır (flexbox/grid değil).
- `!important` karanlık mod bloklarında site CSS'ini geçersiz kılmak için gereklidir.
- `@media print` bloğu karanlık moddan etkilenmez.

## Lisans

Bu tema şablonu tahribat.com topluluğu için oluşturulmuştur.
