# ProductAI Studio

**Turn one product photo into marketing-ready media.**

> Powered by Cloudinary AI transformations for the **Pixels to Products — Cloudinary AI Hackathon 2026** (Track 1 — AI Media Pipelines).

---

## 🚀 Overview

Small businesses, creators, and e-commerce sellers often struggle to prepare high-quality product assets across multiple marketing channels. Manually removing backgrounds, cropping subjects, optimizing file sizes, and reformatting images for Amazon, Instagram, and web stores requires multiple design tools and significant effort.

**ProductAI Studio** solves this challenge by providing an automated, serverless **AI media processing pipeline**. Users upload a single raw product photo, and Cloudinary AI instantly processes, isolates, crops, compresses, and generates multi-platform marketing assets.

---

## 🎯 Problem Statement

- **Time-Consuming Editing**: Sellers spend hours manually cutting out backgrounds and adjusting image aspect ratios for various platforms.
- **Inconsistent Quality**: Scaling photos without smart content-aware cropping distorts products and loses focal detail.
- **Heavy Web Loads**: Unoptimized images degrade page speed, reducing e-commerce conversion rates.
- **Tool Fragmentation**: Sellers hop between photo editors, background removers, and resizers.

---

## 💡 The Solution & Workflow

ProductAI Studio unifies media processing into a single automated 6-stage pipeline:

```
[ User Uploads Product Image ]
               ↓
    [ Next.js App Router ]
               ↓
  [ Next.js API Serverless Route ]
               ↓
[ Cloudinary Node.js SDK Upload ]
               ↓
  [ Cloudinary AI Processing ]
   • e_background_removal (Transparent Cutout)
   • g_auto (Smart Subject Gravity Crop)
   • f_auto, q_auto (Intelligent Format & Quality)
               ↓
 [ Generated Multi-Platform Assets ]
   • Original Photo
   • AI Background Removed PNG
   • WebP Auto-Optimized
   • Amazon Marketplace (1000 × 1000)
   • Instagram Social Post (1080 × 1080)
   • Website Banner (1200 × 800)
               ↓
     [ Instant User Download ]
```

---

## ✨ Features

- **1-Click AI Background Removal**: Isolates product subjects into transparent PNG cutouts using Cloudinary AI (`e_background_removal`).
- **Content-Aware Smart Crop**: Keeps core products centered using gravity auto-detection (`g_auto, c_fill`).
- **Automatic Optimization**: Delivers ultra-fast loading WebP/AVIF formats with dynamic quality compression (`f_auto, q_auto`).
- **Platform Presets**:
  - **Amazon Marketplace**: 1000 × 1000 px (`c_fill,w_1000,h_1000,g_auto,f_auto,q_auto`)
  - **Instagram Feed**: 1080 × 1080 px (`c_fill,w_1080,h_1080,g_auto,f_auto,q_auto`)
  - **Website Banner**: 1200 × 800 px (`c_fill,w_1200,h_800,g_auto,f_auto,q_auto`)
- **Interactive Before / After Slider**: Compare raw uploads against Cloudinary AI cutouts with a draggable slider.
- **Real-Time Visual Pipeline Tracker**: Live status updates across all 6 processing stages.
- **Direct Download & Open**: High-resolution downloadable assets with full URL transparency.
- **Interactive Demo Mode**: Includes pre-configured demo samples for immediate out-of-the-box evaluation.

---

## 🛠️ Cloudinary Features Used

1. **Secure Node.js SDK Upload**: Server-side image upload under `productai-studio` folder namespace.
2. **AI Background Removal**: `e_background_removal` transparent PNG generation.
3. **Smart Focal Crop**: `g_auto, c_fill` for automatic subject retention during resizing.
4. **Auto Format Selection**: `f_auto` to serve optimal image extensions per browser.
5. **Auto Quality Compression**: `q_auto` to balance file size and visual fidelity.
6. **Global CDN Delivery**: Direct high-speed HTTPS asset streaming via Cloudinary edge CDN.

---

## 💻 Tech Stack

- **Framework**: Next.js 16 (App Router)
- **Library**: React 19, TypeScript
- **Styling**: Tailwind CSS v4, Custom Glassmorphism & Micro-animations
- **Media Engine**: Cloudinary Node.js SDK (`cloudinary` v2)
- **Icons**: Lucide React

---

## ⚙️ Environment Variables Setup

Create a `.env.local` file in the root directory:

```env
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

> **Note**: Never expose `CLOUDINARY_API_SECRET` to browser code. All Cloudinary API credentials are used strictly server-side in `app/api/upload/route.ts`.

---

## 🛠️ Installation & Local Development

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-repo/productai-studio.git
   cd productai-studio
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start development server**:
   ```bash
   npm run dev
   ```

4. **Open in browser**:
   Navigate to [http://localhost:3000](http://localhost:3000).

---

## 🚢 Deployment (Vercel)

1. Push your code to GitHub.
2. Connect your repository on [Vercel](https://vercel.com).
3. Add `CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, and `CLOUDINARY_API_SECRET` in Vercel Project Environment Variables.
4. Deploy with one click.

---

## 🏆 Hackathon Details

- **Event**: Pixels to Products — Cloudinary AI Hackathon 2026
- **Track**: Track 1 — AI Media Pipelines
- **Purpose**: Demonstrates how Cloudinary functions as an intelligent end-to-end media automation engine rather than simple image hosting.

---

## 🔮 Future Improvements

- **AI-Generated Contextual Backgrounds**: Swap plain white backgrounds with AI studio lifestyle scenes.
- **Automated Product Descriptions**: Generate SEO marketing copy from product image analysis.
- **Batch Multi-Image Processing**: Upload full catalog zip archives simultaneously.
- **Product Video Shorts**: Generate animated social video clips from still photography.
- **Brand Custom Templates**: Apply watermarks, logos, and custom color overlays automatically.
