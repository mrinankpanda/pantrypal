# 🥫 PantryPal – Smart Recipe Finder with AI

PantryPal is an intelligent iOS app built with Swift and SwiftUI that helps you discover the **6 best recipes** based on the ingredients you have — either by typing them in or snapping a photo of your pantry. It uses a combination of **image recognition**, **local recipe datasets**, and **AI-powered ranking** to generate delicious, relevant meal ideas instantly.

---

## 🚀 Features

### 📝 Ingredient Input
- Add ingredients manually via text
- Autofill suggestions from a preloaded pantry list
- Upload or capture a photo of your pantry to auto-detect food items using image recognition

### 🍽️ Recipe Discovery
- Finds and displays top 6 most relevant recipes based on your ingredients
- Pulls from a local recipe dataset for fast lookup
- Uses AI (OpenAI / Gemini) to rank, summarize, and enhance recipes
- Tap to view detailed recipe info: flavor profile, servings, region, and a short summary

### ✅ Cooking Mode
- Interactive checklist UI to track which ingredients you've used
- Focused, distraction-free cooking experience

### 🔄 Regenerate Recipes
- Didn't like the first 6? Hit “Regenerate” to see the next best suggestions

---

## 🧱 Tech Stack

- **Language:** Swift 5, SwiftUI 3
- **Architecture:** MVVM
- **ML Services:**
  - Image Recognition: Firebase ML Kit or CoreML (Food101 model)
  - Recipe Ranking: OpenAI / Gemini Prompt API
- **Data Source:** Food.com or Recipe1M (cleaned & locally stored as `recipes.json`)
- **State Management:** `@StateObject`, `@ObservedObject`, Combine

---

## 📁 Project Structure

PantryPal/
├── Models/
├── Views/
├── ViewModels/
├── Services/
├── Resources/
├── Extensions/
├── PantryPalApp.swift
└── AppRouter.swift

See [`docs/ProjectStructure.md`](docs/ProjectStructure.md) for full breakdown.

---

## 🧠 How it Works

1. **Input Ingredients**
   - Type manually or take a picture
   - Auto-extract ingredients via ML

2. **Fetch Candidate Recipes**
   - Load top 20+ matching recipes from local JSON dataset

3. **AI Ranks Recipes**
   - User ingredients + candidate recipes → prompt to AI → get best 6 matches

4. **Display Results**
   - Recipes shown with thumbnail, summary, tags
   - Tap to expand

5. **Make It**
   - Enter cooking mode with checklist

---

## 🗃️ Dataset

- Recommended: [Food.com Recipes and Reviews](https://www.kaggle.com/datasets/irkaal/foodcom-recipes-and-reviews)
- Cleaned and formatted into `recipes.json`
- Includes ingredients, instructions, tags, servings, and categories

---

## 📦 Installation

> **Requirements**
> - Xcode 15+
> - iOS 17+
> - Swift 5+
> - Firebase (if using image recognition via ML Kit)
> - OpenAI/Gemini API Key (for AI recipe ranking)

```bash
git clone https://github.com/yourusername/PantryPal.git
cd PantryPal
open PantryPal.xcodeproj

