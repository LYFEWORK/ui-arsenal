---
name: model-viewer
source: ReactBits
source_url: https://reactbits.dev/components/model-viewer
category: components
tags: 3d, model, viewer, interactive, WebGL, product
dependencies: three.js, @react-three/fiber, @react-three/drei
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# ModelViewer

> A 3D model viewer component for displaying and interacting with GLTF/GLB models. Supports orbit controls, auto-rotate, environment lighting, and responsive sizing. Built on React Three Fiber for seamless React integration.

## When to Use

- Product showcase pages where 3D models add value (hardware, physical products)
- Architecture or interior design portfolios with 3D walkthroughs
- SaaS landing pages with a 3D representation of the product
- Interactive brand experiences or microsites
- Educational platforms with 3D anatomy, engineering, or science models

## When NOT to Use

- Standard business websites without 3D assets
- Mobile-first audiences (WebGL is heavy on mobile)
- SEO-critical pages (3D canvas content is not indexable)
- Pages that need to load fast (three.js adds significant bundle weight)
- Client builds without existing 3D assets (creation cost is high)

## Pairs Well With

- `gradient-text` - Gradient heading overlay next to the 3D viewer
- `glass-surface` - Glass panel with product info beside the viewer
- `animated-content` - Fade in the viewer section on scroll
- `aurora` - Aurora background behind the 3D scene

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| modelUrl | string | required | URL to GLTF/GLB model file |
| autoRotate | boolean | true | Auto-rotate the model |
| rotateSpeed | number | 1 | Auto-rotation speed |
| enableZoom | boolean | true | Allow scroll-to-zoom |
| enablePan | boolean | false | Allow click-to-pan |
| environment | string | "studio" | HDR environment preset |
| cameraPosition | [number,number,number] | [0,0,5] | Initial camera position |
| fallback | ReactNode | null | Fallback for unsupported devices |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ModelViewer-TS-TW
```

## Usage Example

```jsx
import { Suspense } from 'react';
import ModelViewer from '@/components/ui/ModelViewer';

function ProductShowcase() {
  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="max-w-6xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div>
          <h2 className="text-4xl font-extrabold text-white font-[Manrope]">
            See It In 3D
          </h2>
          <p className="mt-4 text-gray-400 text-lg">
            Interact with our product. Rotate, zoom, and explore every detail.
          </p>
          <a
            href="/book"
            className="inline-block mt-8 px-6 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold rounded-lg"
          >
            Request a Demo
          </a>
        </div>
        <Suspense fallback={<div className="h-[500px] lyf-glass rounded-xl animate-pulse" />}>
          <ModelViewer
            modelUrl="/models/product.glb"
            autoRotate
            rotateSpeed={0.8}
            environment="studio"
            cameraPosition={[0, 1, 4]}
            className="h-[500px] rounded-xl overflow-hidden"
            fallback={
              <img src="/models/product-fallback.jpg" alt="Product" className="rounded-xl" />
            }
          />
        </Suspense>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Viewer container: `rounded-xl` (12px) with `overflow-hidden` to clip the canvas
- Environment lighting: subtle warm tones to complement Lyfework's orange brand
- Loading skeleton: `lyf-glass animate-pulse` matching the viewer dimensions
- Always provide a static image `fallback` for mobile and low-power devices
- Not GHL compatible -- requires standalone React deployment (Vercel/Netlify)
- Font: `Manrope` 800 for section heading, 400 for description text

## Performance Notes

- three.js + @react-three/fiber + @react-three/drei add ~200KB gzipped; code-split with dynamic import
- Use `Suspense` boundary with a skeleton loader while the 3D scene initializes
- GLB models should be optimized with `gltf-pipeline` or `gltfpack` (target under 2MB)
- `frameloop="demand"` prevents continuous rendering when nothing is animating
- On mobile, disable orbit controls and show a static turntable animation instead
