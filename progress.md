# Session Progress Log: Landing Vastu («Васту-геометрия»)

> **Подпроект:** `landing-vastu` (`vastu.aisukam.ru`)  
> **Стек:** Vite, React 19, TypeScript, Three.js / React Three Fiber, Custom CSS

---

## Текущее верифицированное состояние (Current Verified State)
* **Стандартная верификация:** `pwsh -ExecutionPolicy Bypass -File scripts/verify.ps1 -Subproject landing-vastu`
* **Деплой:** `pwsh -ExecutionPolicy Bypass -File scripts/deploy.ps1 -Subproject landing-vastu` (после оптимизации 3D)
* **Текущий статус:** Подключен через NTFS Junction, билд успешен. Модель `temple.glb` требует оптимизации перед деплоем на прод.

---

## Сессионный журнал подпроекта

### Сессия: 2026-10-26 | Фича 5: Фиксация версий зависимостей и изоляция локальных файлов (Hardening 3.6, 3.7)
* **Цель:** Исключить использование плавающих версий 'latest' в package.json и предотвратить утечку локальных конфигов.
* **Выполнено:**
  1. В package.json все плавающие версии 'latest' заменены на проверенные совместимые диапазоны (React 19.2.5, Vite 8.0.10, TypeScript 6.0.3, ESLint 10.2.1).
  2. В .gitignore добавлены правила desktop.ini, *.local, config.php, lead-config.php.
* **Верификация:** pwsh -ExecutionPolicy Bypass -File scripts/verify.ps1 -Subproject landing-vastu (tsc -b && vite build) успешно пройден за 3.08s (код 0).

### Сессия: 2026-10-13 | Интеграция в Meta-Harness и кастомные скроллбары
* **Цель:** Подключить проект к Meta-Harness, настроить верификацию Vite, стилизовать скроллбар под эстетику сандала и камня.
* **Выполнено:**
  1. Проект смонтирован в `projects/landing-vastu` через NTFS Junction.
  2. Добавлены кросс-браузерные кастомные скроллбары (`styles.css`): храмовый камень + золотой сандал.
  3. Зафиксирован блокер деплоя: модель `temple.glb` весит ~84 МБ, требуется компрессия Draco до <3-5 МБ.
* **Верификация:** `npm run build` (0 ошибок TypeScript и Vite).
* **Git:** Коммит `afb2731` отправлен в GitHub.

---

## Журнал коммитов подпроекта
- **2026-10-13 04:45** | style(vastu): add custom sacred stone and ancient gold scrollbar

- **2026-10-16 23:01** | docs(vastu): add context bridge and seed progress.md

- **2026-10-26 02:25** | security(landing-vastu): pin dependency versions and add gitignore
