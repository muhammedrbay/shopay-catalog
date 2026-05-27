# Ürün Görselleri

Her ürün için `images/<product_id>/` klasörü altında görseller tutulur.

## Yapı

```
images/
├── 1/                  ← Ürün id 1
│   ├── main.webp       ← Ana görsel (is_primary=true)
│   ├── 2.webp
│   └── 3.webp
├── 2/                  ← Ürün id 2
│   └── main.webp
└── ...
```

## Format kuralları

- **Format:** WebP (JPEG/PNG'den %30-50 daha küçük)
- **Maksimum genişlik:** 800px (mobil için yeterli)
- **Hedef boyut:** 30-100 KB/görsel

## URL formatı

Görsel CDN üzerinden şu adresten erişilir:

```
https://cdn.jsdelivr.net/gh/muhammedrbay/shopay-catalog@main/images/<product_id>/<filename>
```

## `products.json` ile bağlantı

`products.json` içinde `product_images` alanı bu URL'leri içerir:

```json
{
  "id": 1,
  "name": "Ürün adı",
  "product_images": [
    {
      "url": "https://cdn.jsdelivr.net/gh/muhammedrbay/shopay-catalog@main/images/1/main.webp",
      "is_primary": true
    }
  ]
}
```

## Yeni görsel/ürün eklerken

1. Görselleri uygun `images/<id>/` klasörüne koy
2. `products.json`'da URL'leri güncelle
3. `version.json` içindeki `v` sayısını **1 arttır**
4. Commit + push
