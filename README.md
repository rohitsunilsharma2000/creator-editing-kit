 
---

# PNG Thumbnail-এ Bengali Text Replace (No PSD) — Photoshop 2026 (Mac) Documentation

## 1) Goal

তোমার কাছে যদি শুধু **PNG** থাকে (PSD না থাকে), তবুও Photoshop 2026-এ:

* পুরোনো Bengali text **remove**
* background **match** করে fade সমস্যা ঠিক করা
* নতুন Bengali text **add + style match**
  —সব করা যাবে।

---

## 2) Why PSD ছাড়া direct edit হয় না?

PNG হলো **flattened image**। Text আলাদা layer হিসেবে থাকে না, তাই “text layer edit” সম্ভব না।
Solution: **old text erase + new text overlay**।

---

# PART A — Old Bengali Text Remove + New Text Add

## Option 1 (সবচেয়ে easy): Old text ঢেকে নতুন text লিখো

### Steps (Photoshop 2026, Mac)

1. **File > Open** → PNG open করো
2. Zoom in: **⌘ +**
3. Tool নাও:

   * **Lasso Tool (L)** অথবা **Marquee Tool (M)**
4. Bengali text area **select** করো
5. Remove করতে:

   * **Edit > Content-Aware Fill…** → Preview দেখে **OK**
   * Alternative: **Shift + F5** → **Content-Aware**
6. এখন area clean হবে (পুরোনো লেখা চলে যাবে)
7. নতুন text বসাতে:

   * **Type Tool (T)** → নতুন Bengali text লিখো
8. Font:

   * **Noto Sans Bengali ExtraBold** (recommended)
9. Style match:

   * Text layer double click → **Drop Shadow**

     * Opacity **25–40%**
     * Distance **6–10**
     * Size **12–18**
   * Optional: **Stroke** (only if needed)

     * Size **2–4 px**
     * Color **#000000**
     * Opacity **20–40%**

✅ Result: PNG হলেও professional দেখাবে।

---

# PART B — Content-Aware Fill এর পরে “Color Fade / Blur” Fix

## Problem

Content-Aware Fill / Generative Fill অনেকসময় background-টা:

* ফেড (lighter/darker)
* ব্লার
* টোন mismatch
  করে দেয়, ফলে ওই জায়গা আলাদা লাগে।

---

## Fix 1 (Fastest): Clone Stamp + Healing (Tone Match)

### Goal

পাশের একই background কপি করে fade অংশে বসানো।

### Steps

1. **New empty layer** বানাও:

   * **Layer > New > Layer…**
   * Name: `Patch`
2. **Clone Stamp Tool** নাও: `S`
3. Top bar-এ সেট করো:

   * **Sample: Current & Below** ✅ (Must)
4. **Option (⌥)** ধরে:

   * fade অংশের পাশের ঠিক background-এ **একবার click** (sample/source)
5. fade অংশে **soft brush** দিয়ে paint করো:

   * Hardness **0%**
   * Opacity **20–40%**
6. Edge smooth করতে:

   * **Spot Healing Brush**: `J` (বা Healing Brush)
   * শুধু edges-এ ছোট stroke

✅ Result: fade অনেকটাই disappear হবে।

---

## Best Workflow (Recommended)

**Clone Stamp (low opacity)** → **Healing Brush** → শেষে **Curves** দিয়ে final match

---

## Quick Settings (Recommended)

* **Clone Stamp**

  * Hardness: **0%**
  * Opacity: **30%**
  * Flow: **20–30%**
  * Sample: **Current & Below**
* **Healing Brush**

  * Only edges, small strokes
* **Curves**

  * Midtone সামান্য up/down (fade অনুযায়ী)

---

# PART C — Final Color Match (Advanced কিন্তু clean)

## Fix 2: Curves শুধুমাত্র patch area-তে

1. fade area select (Lasso)
2. **Layer > New Adjustment Layer > Curves…**
3. Curves-এ midtone adjust করে surrounding background match করো
4. Mask soften:

   * Mask select → Properties → Feather **1–3 px**

---

# PART D — Export (YouTube-ready)

## Save editable file

* **File > Save As… > PSD** (future text change easy)

## Export final

* **File > Export > Export As…**

  * JPG
  * Quality **75–85**

---

# Troubleshooting (Common Issues)

## 1) Clone Stamp কাজ করছে না / weird হচ্ছে

* Patch layer selected? ✅
* Sample: **Current & Below**? ✅ (Current Layer হলে সমস্যা হবে)

## 2) Text দেখা যাচ্ছে না

* Text layer shape layer-এর উপরে আছে কিনা

  * Bring to front: **⌘ ⇧ ]**

## 3) Background এখনও mismatch

* Curves adjustment দিয়ে midtone match করো
* Healing brush দিয়ে edges blend করো

---

## Mini Checklist (Before Upload)

✅ Text readable on mobile?
✅ 2 lines max?
✅ Face highlight + glow ঠিক আছে?
✅ Patch area natural দেখাচ্ছে?
✅ Export JPG quality 75–85?

---

 
