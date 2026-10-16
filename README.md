# @apps4craft/ui — Apps4Craft Unified Design System

Wspólna biblioteka front-endu, tokenów rzemieślniczych i wektorowej ikonografii dla 5 rzemieślniczych aplikacji kuchennych ze studia **Apps4Craft**:
1. ☕ **Napar (Steepwise)** — Kawa Specialty & Herbata Rzemieślnicza (`#C86A28` Warm Copper)
2. 🥖 **Piekarz** — Chleb Rzemieślniczy, Zakwas & Hydratacja (`#D49B42` Golden Crust)
3. 🫙 **Słoik** — Kiszonki, Solanki & Fermentacja Warzyw (`#5B8A61` Dill Herb Green)
4. 🥩 **Masaż / Charcutier** — Wędliny Dojrzewające & Peklowanie (`#A43E38` Smoked Hickory)
5. 🧀 **Ferment** — Sery Rzemieślnicze & Dojrzewalnia (`#E0A838` Aged Gouda)

---

## Instalacja

W dowolnej aplikacji rodziny Apps4Craft:

```bash
npm install github:lkarwowski494/apps4craft-ui
```

Wymagane peer-dependencies: `react`, `react-native`, `react-native-safe-area-context`, `react-native-svg`, `expo-haptics`.

---

## Kluczowe Komponenty

### 1. `CraftHeader` (Gwarancja Bezpiecznej Nawigacji)
Automatycznie respektuje górny margines Safe Area iOS (`Math.max(insets.top, 16)`). Przycisk zamknięcia/powrotu o strefie kliku min. **44×44 pt** z powiększonym `hitSlop` (`±12 pt`) nigdy nie koliduje ze wskaźnikiem baterii ani Dynamiczną Wyspą.

```tsx
import { CraftHeader } from '@apps4craft/ui';

<CraftHeader
  title="Kalkulator Solanki"
  subtitle="Słoik Craft Suite"
  onClose={() => setOpen(false)}
/>
```

### 2. `CraftModal`
Pełnoekranowy ceramiczny modal (`#121214`) z wbudowanym `CraftHeader`, obsługą klawiatury i przyklejoną stopką:

```tsx
import { CraftModal, CraftButton } from '@apps4craft/ui';

<CraftModal
  visible={isOpen}
  onClose={() => setIsOpen(false)}
  title="Nowy Zakwas Żytni"
  subtitle="Piekarz Craft Suite"
  footer={
    <CraftButton
      label="ROZPOCZNIJ RYTUAŁ"
      accentColor="#D49B42"
      onPress={handleSave}
    />
  }
>
  {/* Formularz */}
</CraftModal>
```

### 3. `CraftStatDisplay` (*"The Sacred Numbers"*)
Minimalistyczna prezentacja kluczowych parametrów z tabulowanym krojem (`tabular-nums`), czytelna z odległości 1 metra na blacie kuchennym:

```tsx
import { CraftStatDisplay } from '@apps4craft/ui';

<CraftStatDisplay
  label="Hydratacja"
  value="75"
  unit="%"
  accentColor="#D49B42"
  subtext="Chleb pszenno-żytni"
/>
```

### 4. `CraftButton`
Haptyczny przycisk kuchenny o wysokości min. **52 pt** z obsługą wariantów (`primary`, `secondary`, `ghost`, `danger`) i stanu `loading`.

---

## Tokeny i Motywy

```tsx
import { CRAFT_APPS, getCraftTheme, sharedCraftTokens } from '@apps4craft/ui';

const theme = getCraftTheme('piekarz');
console.log(theme.accent); // '#D49B42'
```

---

## Ikony Wektorowe SVG

Zero emoji, spójny obrys (stroke 1.75pt / 2.0pt), pełna ostrość:
* `BrewIcon`, `BeansIcon`, `JournalIcon`, `LabIcon`, `CaffeineIcon`, `SettingsIcon`, `GrinderIcon`
* `PlayIcon`, `PauseIcon`, `NextStepIcon`, `PrevStepIcon`, `ResetIcon`, `QrIcon`, `StarIcon`
* `NaparAppIcon`, `PiekarzAppIcon`, `SloikAppIcon`, `MasazAppIcon`, `FermentAppIcon`, `CraftFamilyEmblem`
* `ChevronBackIcon`, `CloseIcon`

---

## Licencja
MIT — Apps4Craft Studio
