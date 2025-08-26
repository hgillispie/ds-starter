# Chargebee Design System — Authoritative Tokens  
*(Last updated 2025-08-19)*  
#ALWAYS REFER TO Sting Vuew MCP SERVER FOR DESIGN SYSTEM COMPONENTS AND TOKENS
https://sting-vue-mcp-sse.localcblabs.com/sse 

---

## 🔒 Global Usage Rules  

1. **Use a token whenever one exists** (`para-regular`, `primary-500`, etc.).  
2. If **no suitable token** is defined for the required property, **use the closest Tailwind utility class** (`text-3xl`, `rounded-md`, `p-4`, etc.).  
3. Only if both the token set **and** Tailwind lack the needed value may you write custom CSS or hard-code a value.  
4. When you do need to fall back, prefer a Tailwind class over custom CSS.  
5. Never mix tokens and conflicting Tailwind classes on the same element; the token should win.  
6. When in doubt, ask for a new token rather than guessing.

---

## 1. Colour Tokens  — *Use these first; Tailwind colours only as fallback*

<details>
<summary>Primary (`primary-*`)</summary>

| Token | Hex |
|-------|-----|
| `primary-25` | #FBFDFF |
| `primary-50` | #F2F7FF |
| `primary-100` | #D7E6FD |
| `primary-200` | #ABC9F9 |
| `primary-300` | #7BA8F3 |
| `primary-400` | #4B84E2 |
| `primary-500` | #1961D3 |
| `primary-600` | #084DB4 |
| `primary-700` | #003B92 |
| `primary-800` | #002A6E |
| `primary-900` | #011D50 |
| `primary-1000` | #041638 |
</details>

<details>
<summary>Neutral (`neutral-*`)</summary>

| Token | Hex |
|-------|-----|
| `neutral-0` | #FFFFFF |
| `neutral-25` | #FBFCFD |
| `neutral-50` | #F3F5F8 |
| `neutral-100` | #E5E8ED |
| `neutral-200` | #C9CED6 |
| `neutral-300` | #A7AEBB |
| `neutral-400` | #86909F |
| `neutral-500` | #545E6F |
| `neutral-600` | #3B4350 |
| `neutral-700` | #2E3642 |
| `neutral-800` | #1C222B |
| `neutral-900` | #090B0F |
</details>

<details>
<summary>Success (`success-*`)</summary>

| Token | Hex |
|-------|-----|
| `success-25` | #FAFEFA |
| `success-50` | #F1FAF1 |
| `success-100` | #D7EBD7 |
| `success-200` | #A9D5AA |
| `success-300` | #75BC78 |
| `success-400` | #3D9D46 |
| `success-500` | #008020 |
| `success-600` | #006818 |
| `success-700` | #005211 |
| `success-800` | #003C0A |
| `success-900` | #002B05 |
| `success-1000` | #002003 |
</details>

<details>
<summary>Warning (`warning-*`)</summary>

| Token | Hex |
|-------|-----|
| `warning-25` | #FFFDF6 |
| `warning-50` | #FEF7E1 |
| `warning-100` | #FDEEC1 |
| `warning-200` | #FFE79C |
| `warning-300` | #FFDF7B |
| `warning-400` | #FFD95E |
| `warning-500` | #FED33E |
| `warning-600` | #E8C031 |
| `warning-700` | #CFAA23 |
| `warning-800` | #AC8C0E |
| `warning-900` | #786100 |
| `warning-1000` | #584600 |
</details>

<details>
<summary>Danger (`danger-*`)</summary>

| Token | Hex |
|-------|-----|
| `danger-25` | #FFFCFC |
| `danger-50` | #FFF4F3 |
| `danger-100` | #FBDCDA |
| `danger-200` | #F5B5B1 |
| `danger-300` | #EA8884 |
| `danger-400` | #D35958 |
| `danger-500` | #BA2A33 |
| `danger-600` | #A00D21 |
| `danger-700` | #810016 |
| `danger-800` | #61000E |
| `danger-900` | #460108 |
| `danger-1000` | #320608 |
</details>

<details>
<summary>Info (`info-*`)</summary>

| Token | Hex |
|-------|-----|
| `info-25` | #F4FEFE |
| `info-50` | #E3FBFC |
| `info-100` | #C7EDEF |
| `info-200` | #9DD3D5 |
| `info-300` | #70B5B9 |
| `info-400` | #429599 |
| `info-500` | #10777C |
| `info-600` | #066166 |
| `info-700` | #004C50 |
| `info-800` | #00383B |
| `info-900` | #00282A |
| `info-1000` | #001B1C |
</details>

<details>
<summary>Brand</summary>

| Token | Hex |
|-------|-----|
| `brand-logo` | #FF3300 |
| `brand-logo-light` | #FF523B |
| `brand-deep-dark` | #012A38 |
| `brand-deep-light` | #E6EAEB |
| `brand-lime-dark` | #344303 |
| `brand-lime-light` | #BFF90B |
| `brand-blue-dark` | #293031 |
| `brand-blue-light` | #A2C1C4 |
| `brand-ivory-dark` | #383732 |
| `brand-ivory-light` | #E0DBC6 |
</details>

---

## 2. Typography Tokens  

> **Use these first.** If a specific size/weight isn’t covered, fall back to the closest Tailwind text utility (`text-lg`, `font-semibold`, etc.).  

| Token | Size | Line-height | Weight | Letter-spacing |
|-------|------|-------------|--------|----------------|
| `tiny-regular`   | 10px / 0.625rem | 16px / 1rem  | Regular  | 0 |
| `tiny-medium`    | 10px / 0.625rem | 16px / 1rem  | Medium   | 0 |
| `tiny-semibold`  | 10px / 0.625rem | 16px / 1rem  | Semibold | 0 |
| `caption-regular`| 12px / 0.75rem  | 16px / 1rem  | Regular  | 0 |
| `caption-medium` | 12px / 0.75rem  | 16px / 1rem  | Medium   | 0 |
| `caption-semibold`|12px / 0.75rem  | 16px / 1rem  | Semibold | 0 |
| `para-regular`   | 14px / 0.875rem | 20px / 1.25rem| Regular | 0 |
| `para-medium`    | 14px / 0.875rem | 20px / 1.25rem| Medium  | 0 |
| `para-semibold`  | 14px / 0.875rem | 20px / 1.25rem| Semibold| 0 |
| `lead-regular`   | 16px / 1rem     | 24px / 1.5rem | Regular | 0 |
| `lead-medium`    | 16px / 1rem     | 24px / 1.5rem | Medium  | 0 |
| `lead-semibold`  | 16px / 1rem     | 24px / 1.5rem | Semibold| 0 |
| `heading-3xl`    | 48px / 3rem     | 56px / 3.5rem| Semibold| -0.32px |
| `heading-2xl`    | 32px / 2rem     | 40px / 2.5rem| Semibold| -0.24px |
| `heading-xl`     | 24px / 1.5rem   | 32px / 2rem  | Semibold| -0.16px |
| `heading-lg`     | 24px / 1.5rem   | 28px / 1.75rem| Semibold| -0.08px |
| `heading-md`     | 16px / 1rem     | 24px / 1.5rem | Semibold| 0 |
| `heading-sm`     | 14px / 0.875rem | 20px / 1.25rem| Semibold| 0 |

---

## 3. Radius Tokens  

> **Use these first.** If an exact radius isn’t available, fall back to the closest Tailwind `rounded-*` class, or custom CSS as a last resort.

| Token | Value |
|-------|-------|
| `radius-none` | 0 |
| `radius-sm` | 2px / 0.125rem |
| `radius-st` | 4px / 0.25rem |
| `radius-md` | 6px / 0.375rem |
| `radius-lg` | 8px / 0.5rem |
| `radius-xl` | 12px / 0.75rem |
| `radius-circular` | 999px |

---

## 4. Spacing Tokens  

> **Use these first.** If you need a spacing value not in this table, use the appropriate Tailwind spacing utility (`p-3`, `gap-2`, etc.). Only hard-code numbers when neither list covers the case.

| Token | Value |
|-------|-------|
| `space-none` | 0 |
| `space-si` | 2px / 0.125rem |
| `space-ti` | 4px / 0.25rem |
| `space-ni` | 6px / 0.375rem |
| `space-mi` | 8px / 0.5rem |
| `space-xs` | 12px / 0.75rem |
| `space-sm` | 16px / 1rem |
| `space-st` | 20px / 1.25rem |
| `space-md` | 24px / 1.5rem |
| `space-lg` | 32px / 2rem |
| `space-xl` | 36px / 2.25rem |
| `space-2xl` | 40px / 2.5rem |
| `space-3xl` | 48px / 3rem |
| `space-4xl` | 56px / 3.5rem |
| `space-5xl` | 64px / 4rem |
| `space-6xl` | 72px / 4.5rem |
| `space-7xl` | 80px / 5rem |
