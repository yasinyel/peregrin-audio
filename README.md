# Peregrin sesli anlatım kayıtları

Uygulamanın anlatım kayıtlarının (ElevenLabs) asıl kopyası. Uygulama sesleri buradan değil, Cloudflare R2'den
("peregrin-audio" deposu, peregrin-sat sunucusu üzerinden) alır.

- `audio/<rota>/<dil>/<anahtar>.mp3`: kayıtlar (rota `common` ortak cümleler)
- `audio/manifest.json`: { rota: { dil: { anahtar: bayt } } }, `audio/index.json`: { rota: { dil: [anahtar] } }

Üretim: peregrin deposunda `python3 tools/narrate.py <rota> <diller> --audio ../peregrin-audio/audio`.
Yükleme: peregrin deposunda "Sesleri Cloudflare'e yükle" işi (bu depodan paketler üretip R2'ye yükler).
