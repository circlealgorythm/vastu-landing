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
