## Tuana Sitesi Aidat Takibi

Uygulama `localStorage` kullanmaz. Yönetici ana sayfada blok ve daire seçebilir, önceki/sonraki daireye geçebilir ve seçili daire için paylaşım bağlantısını kopyalayabilir. `?unit=<rastgele-kod>` biçimindeki bağlantı yalnızca o dairenin ekranını açar.

Her dairenin verisi `data/units/<rastgele-kod>.json` dosyasındadır. Yönetici listesini `data/admin-index.json` tutar. Yeni daire eklerken yeni bir rastgele kodla JSON dosyası oluşturup aynı kodu manifestteki `token` alanına ekleyin. Aylık ödeme anahtarları `01` ile `12` arasındadır; yıl ve ay kayıtları `payments` alanında bulunur.

Dosyalar statik ve salt okunurdur: ödeme bilgisi değiştirmek için JSON dosyasını güncelleyip yeniden yayımlayın. Rastgele bağlantı bir erişim anahtarıdır, ancak statik hosting gerçek kimlik doğrulama sağlamaz; yayımlanan JSON ve yönetici manifesti URL'lerini bilen kişiler dosyaları okuyabilir. Hassas veriler için sunucu tarafı yetkilendirme gerekir.

Geliştirme sırasında sayfayı HTTP üzerinden sunun; `file://` ile JSON `fetch` istekleri çalışmaz.
