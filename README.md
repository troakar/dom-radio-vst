# D O M  •  R A D I O  •  S U I T E

> **Maestro-Tape Emulation Suite • Маэстро-магнитофон**  
> Inspired by Soviet audio engineering, Makhachkala 1978 • ГОСТ 20838-75.

---

### Language / Язык:
* 🇺🇸 [English Presentation](#-english-version)
* 🇷🇺 [Русское описание](#-русская-версия)

---

## 🇺🇸 English Version

![Dom Radio Suite Overview](assets/screenshot_master.png)

**Dom Radio Suite** is a collection of high-end tape emulation plugins designed to bring the warm, nonlinear, and distinct character of vintage Soviet radio-broadcasting tape equipment to your modern DAW. 

The suite contains three tailored editions:
1. **Dom Radio Master** — Full-featured mastering processor with TMT (Tolerance Modeling Technology), advanced tape mechanics simulation, age wear, CRT frequency display, and Pultec/Emphasis tone shapers.
2. **Dom Radio Track** — CPU-optimized edition for individual mixing tracks, featuring core saturation, essential tape speed controls, and smart detail enhancement.
3. **Dom Radio Drive** — Focused saturation unit centered around Germanium and Silicon preamp stages.

### 🌟 Key Features
* **Dual Distortion Engine:** Toggle between Silicon (symmetric, odd harmonics) and Germanium (asymmetric, even harmonics) vintage preamp stages.
* **Physical Tape Core:** True non-linear Langevin hysteresis modeling with independent Bias and Sag controls.
* **Tolerance Modeling Technology (TMT):** Simulates component variances (resistors, capacitors, transistor beta) between left and right channels for a natural, deep stereo field.
* **Archive '84 Unit:** Age macro-control, oxide dropouts, wow & flutter, scrape flutter, azimuth drift, and vintage mains hum sampled directly from Dagestan radio archives.
* **Detail Extractor:** Upward compression algorithms (Wideband & Multiband) to bring out subtle textures without destroying transients. *Modern Detail Extractor (Musical Upward Compressor)* — secret weapon for electronic producers and old-school sampling. It gently lifts buried micro-textures, tails and attacks from the track depths, instantly saturating them with analog tape warmth without harsh digital edge.
* **CRT Oscilloscope Display:** Real-time frequency visualization with phosphor decay and THD-reactive beam swelling.

### 📦 Installation & Quick Start

#### macOS (VST3 / AU)
1. Download the latest macOS release archive from the [Releases](../../releases) page.
2. Move `.vst3` files to `/Library/Audio/Plug-Ins/VST3/`.
3. Move `.component` files to `/Library/Audio/Plug-Ins/Components/`.
4. **Bypass Apple Gatekeeper Quarantine (Required for ad-hoc builds):**
   Open Terminal and run:
   ```bash
   sudo xattr -cr "/Library/Audio/Plug-Ins/VST3/DOM RADIO MASTER.vst3"
   sudo xattr -cr "/Library/Audio/Plug-Ins/Components/DOM RADIO MASTER.component"
   ```

#### Windows (VST3)
1. Download the latest Windows release archive from the [Releases](../../releases) page.
2. Copy the `.vst3` folders to `C:\Program Files\Common Files\VST3\`.

---

## 🇷🇺 Русская Версия

![Dom Radio Suite Overview](assets/screenshot_track.png)

**Dom Radio Suite** — это набор плагинов эмуляции магнитной ленты, разработанный для воссоздания теплого, нелинейного и харизматичного характера советской студийной и вещательной аппаратуры конца 1970-х годов.

В состав набора входят три редакции:
1. **Dom Radio Master** — Полнофункциональный мастер-процессор с системой моделирования допусков компонентов (TMT), детальной симуляцией физики лентопротяжного механизма, старением магнитных головок, CRT-дисплеем и тональной коррекцией.
2. **Dom Radio Track** — Оптимизированная по нагрузке на процессор версия для сведения отдельных дорожек с ключевым насыщением, регулировкой скорости и умным выделением деталей.
3. **Dom Radio Drive** — Специализированный сатуратор, сфокусированный на германиевых и кремниевых каскадах предусиления.

### 🌟 Ключевые Особенности
* **Двойной каскад перегруза:** Переключение между кремниевым (Silicon) и германиевым (Germanium) транзисторными предусилителями.
* **Магнитное ядро:** Моделирование петли гистерезиса Ланжевена с настройкой тока подмагничивания (Bias) и просадки напряжения (Sag).
* **Tolerance Modeling Technology (TMT):** Воссоздает естественный разброс радиодеталей левого и правого каналов для получения естественной аналоговой стереобазы.
* **Блок архивации '84:** Макро-регулятор возраста пленки, выпадение окисла (dropouts), детонация (wow & flutter), азимут и сэмплы шума из архивов радиовещания Дагестана.
* **Экстрактор деталей:** Алгоритмы восходящей компрессии (Wideband и Multiband) для вытаскивания скрытых текстур. *Modern Detail Extractor (Musical Upward Compressor)* — секретное оружие для электронных продюсеров и работы со старыми сэмплами. Модуль деликатно поднимает из глубины трека запрятанные микро-текстуры, шлейфы и атаки, мгновенно насыщая их аналоговым теплом магнитной ленты без едкой цифровой резкости.
* **CRT-Дисплей:** Визуализация АЧХ с эффектом затухания люминофора и реакцией луча на уровень гармоник.

### 📦 Установка

#### macOS (VST3 / AU)
1. Скачайте архив из раздела [Releases](../../releases).
2. Скопируйте папки `.vst3` в `/Library/Audio/Plug-Ins/VST3/`.
3. Скопируйте папки `.component` в `/Library/Audio/Plug-Ins/Components/`.
4. **Снятие карантина Apple (Gatekeeper):**
   Откройте Терминал и выполните:
   ```bash
   sudo xattr -cr "/Library/Audio/Plug-Ins/VST3/DOM RADIO MASTER.vst3"
   sudo xattr -cr "/Library/Audio/Plug-Ins/Components/DOM RADIO MASTER.component"
   ```

#### Windows (VST3)
1. Скачайте архив из раздела [Releases](../../releases).
2. Скопируйте папки `.vst3` по пути `C:\Program Files\Common Files\VST3\`.

### 📄 Руководства пользователя
* [🇬🇧 English User Manual](manuals/Manual_EN.md)
* [🇷🇺 Руководство пользователя на русском](manuals/Manual_RU.md)

---

*Built with JUCE • Inspired by Mechlabor 610 • Makhachkala 1978*
