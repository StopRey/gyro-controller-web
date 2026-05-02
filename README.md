# gyro-controller-web

Статична сторінка для керування орієнтацією телефона: `deviceorientation` → Socket.IO relay → Unity (або інший клієнт у тій самій кімнаті).

## Налаштування перед деплоєм

У [`index.html`](index.html) знайди блок `CONFIG` і вистав реальний URL бекенду (Render), **без** слеша в кінці:

```js
const CONFIG = { SOCKET_SERVER_URL: 'https://your-service.onrender.com' };
```

Після зміни закоміть і запуш — GitHub Pages оновиться з нового коміту.

## GitHub Pages

1. Репозиторій на GitHub (наприклад `yourname/gyro-controller-web`).
2. **Settings → Pages → Build and deployment**
3. **Source:** Deploy from a branch.
4. **Branch:** `main`, папка **`/` (root)**.
5. Збережи. Сайт буде за адресою `https://<user>.github.io/gyro-controller-web/` (або custom domain).

Відкривай сторінку з **`?room=XXXX`**, де `XXXX` — той самий room ID, що показує Unity.

## Локальна перевірка

Потрібен HTTPS або localhost для доступу до гіроскопа. Наприклад:

```bash
npx --yes serve -l 3000
```

Відкрий `http://localhost:3000/?room=1234` (на десктопі гіроскоп може бути недоступний — тестуй на телефоні в тій самій мережі або через тунель з HTTPS).
