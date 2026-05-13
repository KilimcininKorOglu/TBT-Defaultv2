# Defaultv2 - tahribat.com Tema Sablonu

tahribat.com icin kullanici tarafindan ozellestirilebilir CSS tema sablonu. Fork'layip kendi temanizi olusturun.

## Ozellikler

- Otomatik karanlik mod (isletim sistemi tercihine gore)
- 70+ CSS degiskeni ile kolay renk ozellestirmesi
- Duyarli tasarim (masaustu, tablet, mobil)
- Yazici dostu baski stilleri
- Build sistemi veya JavaScript gerektirmez

## Dosyalar

| Dosya              | Kapsam                                                    |
| ------------------ | --------------------------------------------------------- |
| `main.css`         | Genel stiller, tasarim degiskenleri, karanlik mod, formlar, tablolar, yorumlar, sayfalama |
| `DefaultPage.css`  | 3 sutunlu sayfa duzeni, duyarli daraltma                  |
| `ForumView.css`    | Forum gonderi gorunumu, avatar paneli, alinti bloklari     |
| `tbtmenu2.css`     | Ust navigasyon menusu, mobil hamburger menusu              |
| `stylus-inject.css`| 4 CSS dosyasinin birlesmis hali (test icin)               |

## Kurulum

1. Bu repoyu fork'layin
2. CSS dosyalarini duzenleyin
3. tahribat.com tema ayarlarindan dosyalarinizi yukleyin

## Karanlik Mod

Karanlik mod, isletim sistemi veya tarayici `prefers-color-scheme: dark` tercih ettiginde otomatik olarak aktif olur. Manuel gecis butonu yoktur.

Tum renkler `:root` icindeki CSS degiskenleri uzerinden yonetilir:

```css
:root {
  --color-bg-page: #ecf0f1;      /* Acik mod */
  --color-text-primary: #333333;
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-bg-page: #121212;     /* Karanlik mod */
    --color-text-primary: #e0e0e0;
  }
}
```

Renkleri degistirmek icin `:root` bloklarindaki degiskenleri duzenleyin.

## Duyarli Tasarim

| Kirilma Noktasi | Davranis                                        |
| --------------- | ----------------------------------------------- |
| >980px          | 3 sutunlu masaustu duzeni                       |
| 980px           | 2 sutun yan yana, orta alan tam genislik        |
| 600px           | Tek sutun duzeni                                |
| 480px           | Yan panel gizlenir, hamburger menu aktif olur   |

## Ozellestirme

### Renk Degistirme

`main.css` dosyasindaki `:root` bloklarinda CSS degiskenlerini duzenleyin. Her degiskenin acik ve karanlik mod degeri vardir.

Ornek renk degiskenleri:

| Degisken                  | Aciklama           |
| ------------------------- | ------------------ |
| `--color-bg-page`         | Sayfa arka plani   |
| `--color-bg-surface`      | Kart arka planlari |
| `--color-text-primary`    | Ana metin rengi    |
| `--color-link`            | Baglanti rengi     |
| `--color-nav-bg`          | Menu arka plani    |
| `--color-border`          | Genel cerceve      |

### Yeni Stil Ekleme

- Genel stiller: `main.css`
- Sayfa duzeni: `DefaultPage.css`
- Forum gonderi stilleri: `ForumView.css`
- Navigasyon menusu: `tbtmenu2.css`

## Yerel Test

Degisikliklerinizi canli sitede test etmek icin:

1. Tum dosyalari birlestirin:
   ```bash
   cat main.css DefaultPage.css ForumView.css tbtmenu2.css > stylus-inject.css
   ```
2. [Stylus](https://github.com/openstyles/stylus) tarayici eklentisini kurun
3. tahribat.com icin yeni bir stil olusturup `stylus-inject.css` icerigini yapistirin
4. Sayfayi yenileyerek degisiklikleri gorun

## Teknik Notlar

- Build adimi yoktur. CSS dosyalarini dogrudan duzenleyin.
- Platform HTML yapisini degistiremezsiniz, yalnizca CSS duzenlenebilir.
- Float tabanli duyarli duzeni kullanilir (flexbox/grid degil).
- `!important` karanlik mod bloklarinda site CSS'ini gecersiz kilmak icin gereklidir.
- `@media print` blogu karanlik moddan etkilenmez.

## Lisans

Bu tema sablonu tahribat.com toplulugu icin olusturulmustur.
