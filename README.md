```md
# ⚛️ React Clone (in TypeScript) — Build React from Scratch

> A fully working mini React clone written in 100% TypeScript — under ~2000 lines — that covers 90% of React's core behavior. Understand React **internals**, not just how to use it.

## 🧠 Why This Exists

Most developers **use** React. Very few understand **how React works under the hood** — from JSX to VDOM, hooks, reconciliation, scheduling, and rendering.

This project is for those who want to:

- Master React internals by rebuilding them
- Understand the full lifecycle of rendering & updates
- Learn how `useState`, `useEffect`, context, and refs actually work

## 🚀 Features Implemented

| Feature                           | Status  | File(s) / Modules                           |
| --------------------------------- | ------- | ------------------------------------------- |
| JSX → Virtual DOM                 | ✅ Done | `core/createElement.ts`                     |
| Functional Components             | ✅ Done | `runtime/component.ts`                      |
| Virtual DOM + Reconciliation      | ✅ Done | `core/reconcile.ts`                         |
| DOM Rendering (initial + update)  | ✅ Done | `core/render.ts`, `dom/domUtils.ts`         |
| `useState`                        | ✅ Done | `hooks/useState.ts`                         |
| `useEffect`                       | ✅ Done | `hooks/useEffect.ts`                        |
| `useRef`                          | ✅ Done | `hooks/useRef.ts`                           |
| `createContext` / `useContext`    | ✅ Done | `runtime/context.ts`, `hooks/useContext.ts` |
| JSX Fragments (`<>...</>`)        | ✅ Done | `runtime/fragment.ts`                       |
| Synthetic Event System            | ✅ Done | `dom/syntheticEvents.ts`                    |
| Scheduler (`requestIdleCallback`) | ✅ Done | `core/scheduler.ts`                         |
| Fiber (simplified)                | ✅ Done | `core/fiber.ts`                             |

> ❌ Not included: Suspense, Concurrent Mode, React Native, DevTools, Error Boundaries

## 📁 Project Structure

react-clone/
├── src/
│ ├── core/ # Core rendering and VDOM logic
│ ├── hooks/ # Custom hook implementations
│ ├── runtime/ # Component runtime & context
│ ├── dom/ # DOM update utils + event delegation
│ ├── types/ # TS types for VDOM, hooks, etc.
│ ├── react/ # Public API surface (like 'react'+'react-dom')
│ ├── client/ # Entry point and example `App`
├── public/ # HTML shell (index.html)
├── tsconfig.json # TypeScript config (strict mode)
├── vite.config.ts # Vite config for dev server/bundling
├── package.json # Scripts and dependencies
└── README.md # You're reading this
```

---

## 🛠️ How to Run

```bash
# 1. Install dependencies
npm install

# 2. Start dev server (Vite)
npm run dev

# 3. Open in browser
http://localhost:5173
```

> Uses `vite` + `typescript` only — no React or JSX runtime dependencies.

---

## 🔍 Example App

Located in `src/client/App.tsx`:

```tsx
import { useState, useEffect } from "../react";

export function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Component mounted or count changed:", count);
  }, [count]);

  return (
    <>
      <h1>Hello from Mini React!</h1>
      <button onClick={() => setCount(count + 1)}>Clicked {count} times</button>
    </>
  );
}
```

---

## 📦 Public API

Exports from `src/react/index.ts` and `src/react/dom.ts`:

```ts
// react/index.ts
export { createElement, Fragment } from "../core/createElement";
export { useState } from "../hooks/useState";
export { useEffect } from "../hooks/useEffect";
export { useRef } from "../hooks/useRef";
export { createContext } from "../runtime/context";
export { useContext } from "../hooks/useContext";

// react/dom.ts
export { render } from "../core/render";
```

---

## ✅ What You'll Learn (React Internals)

| React Feature            | Mastery by Building This |
| ------------------------ | ------------------------ |
| JSX → VDOM               | ✅ 100%                  |
| Rendering Logic          | ✅ 100%                  |
| Reconciliation / Diffing | ✅ 100%                  |
| Hooks Internals          | ✅ 100%                  |
| `useState` / `useEffect` | ✅ 100%                  |
| Context API              | ✅ 100%                  |
| `useRef`                 | ✅ 100%                  |
| Synthetic Events         | ✅ 90%                   |
| Fiber + Scheduler        | ✅ 90%                   |
| Fragments                | ✅ 100%                  |

> 📊 **Overall React Understanding**: \~**90% of modern React** (excluding SSR, Suspense, DevTools)

---

## 💡 Motivation

Rebuilding React gives you confidence and understanding that:

- Makes debugging easier
- Improves your architectural thinking
- Prepares you for interviews and senior roles
- Makes you a real **React expert**, not just a user

---

## 📚 Credits / Inspiration

- [Didact by Dan Abramov](https://github.com/pomber/didact)
- React Fiber architecture notes
- React source code (open source internals)

---

## 🧠 Future Additions (Optional)

- `useMemo`, `useCallback`
- `useReducer`
- Concurrent rendering / better scheduler
- Suspense & Lazy loading
- DevTools hooks

---

## 📜 License

MIT — free to learn and use.

---

## 🌟 Want to Learn by Building?

Start from `src/core/createElement.ts` and walk your way up through:

- VDOM
- `render()`
- Reconciliation
- Hook system
- Components & context

> Every file is <200 LOC and deeply commented. Understand React, don't just use it.

