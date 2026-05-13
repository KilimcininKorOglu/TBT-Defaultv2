# Defaultv2 Dark - tahribat.com Karanlık Tema

tahribat.com için karanlık mod CSS teması. Fork'layıp kendi renk paletinizi oluşturun.

## Özellikler

- Her zaman karanlık tema
- 70+ CSS değişkeni ile kolay renk özelleştirmesi
- Duyarlı tasarım (masaüstü, tablet, mobil)
- Yazıcı dostu baskı stilleri
- Build sistemi veya JavaScript gerektirmez

## Dosyalar

| Dosya               | Kapsam                                                                    |
| ------------------- | ------------------------------------------------------------------------- |
| `main.css`          | Genel stiller, tasarım değişkenleri, formlar, tablolar, yorumlar, sayfalama |
| `DefaultPage.css`   | 3 sütunlu sayfa düzeni, duyarlı daraltma                                 |
| `ForumView.css`     | Forum gönderi görünümü, avatar paneli, alıntı blokları                   |
| `tbtmenu2.css`      | Üst navigasyon menüsü, mobil hamburger menüsü                            |
| `stylus-inject.css` | 4 CSS dosyasının birleşmiş hali (test için)                              |

## Kurulum

1. Bu repoyu fork'layın
2. CSS dosyalarını düzenleyin
3. tahribat.com tema ayarlarından dosyalarınızı yükleyin

## Renk Sistemi

Tüm renkler `main.css` dosyasının başındaki `:root` bloğunda CSS değişkenleri olarak tanımlıdır:

```css
:root {
  color-scheme: dark;
  --color-bg-page: #121212;
  --color-text-primary: #e0e0e0;
  --color-link: #6ea8e8;
  /* ... 70+ değişken */
}
```

Renkleri değiştirmek için `:root` bloğundaki değişkenleri düzenleyin. Tüm siteye otomatik yansır.

Örnek değişkenler:

| Değişken               | Açıklama           |
| ---------------------- | ------------------ |
| `--color-bg-page`      | Sayfa arka planı   |
| `--color-bg-surface`   | Kart arka planları |
| `--color-text-primary` | Ana metin rengi    |
| `--color-link`         | Bağlantı rengi     |
| `--color-nav-bg`       | Menü arka planı    |
| `--color-border`       | Genel çerçeve      |

## Duyarlı Tasarım

| Kırılma Noktası | Davranış                                      |
| --------------- | --------------------------------------------- |
| >980px          | 3 sütunlu masaüstü düzeni                     |
| 980px           | 2 sütun yan yana, orta alan tam genişlik      |
| 600px           | Tek sütun düzeni                              |
| 480px           | Yan panel gizlenir, hamburger menü aktif olur |

## Yeni Stil Ekleme

- Genel stiller: `main.css`
- Sayfa düzeni: `DefaultPage.css`
- Forum gönderi stilleri: `ForumView.css`
- Navigasyon menüsü: `tbtmenu2.css`

## Yerel Test

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
- Float tabanlı duyarlı düzen kullanılır (flexbox/grid değil).
- Sitenin kendi CSS dosyalarını geçersiz kılmak için `!important` gereklidir.
- `@media print` bloğu karanlık temadan etkilenmez.

## Lisans

Bu tema şablonu tahribat.com topluluğu için oluşturulmuştur.
