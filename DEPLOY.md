# نشر الدعوة

المتطلبات: Node.js 22.13+ أو 24 وpnpm 11.25.0. من جذر المشروع: `pnpm install && pnpm build`. الناتج الوحيد المطلوب للنشر هو `dist/`. الموقع Static بلا Functions أو SSR أو قاعدة بيانات.

| الخدمة | إعداد البناء | مجلد النشر |
| --- | --- | --- |
| Vercel | Framework Preset: Vite أو Other، Build Command: `pnpm build` | `dist` |
| Netlify | اربط المستودع؛ `netlify.toml` يحدد `pnpm build` | `dist` |
| Render Static Site | Build Command: `pnpm build` | `dist` |
| Cloudflare Pages | Framework: Vite/React أو None، Build Command: `pnpm build`، Node.js 22 أو 24 | `dist` |
| GitHub Pages | ابنِ بـ `pnpm build` ثم انشر محتويات `dist/` عبر GitHub Actions/Pages | `dist` |

استخدم جذر المستودع كـ Root Directory. المسارات في الناتج نسبية لدعم موقع GitHub Pages تحت مسار المستودع. يمكن أيضًا رفع محتويات `dist/` مباشرة إلى أي استضافة HTML/CSS/JS. لا ترفع `node_modules/` أو `dist/` إلى Git؛ يتم بناؤه على منصة النشر. بعد تحديد نطاق نهائي، يمكن ضبط صورة معاينة المشاركة في `index.html` إلى URL مطلق إذا تطلبت منصة التواصل ذلك، لكن زر المشاركة ورابط واتساب يعملان تلقائيًا بنطاق الموقع المنشور.
