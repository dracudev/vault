Next.js uses a **file-based routing system** where the structure of the `app/` directory directly defines your application's routes. Each folder and file represents a route.

```arduino
app/
├── page.tsx         // Root-level route ("/")
├── layout.tsx       // Root-level layout
├── about/
│   ├── page.tsx     // "/about" route
│   └── layout.tsx   // Layout specific to "/about"
├── contact/
│   └── page.tsx     // "/contact" route
├── product/
│   └── [id]     // "/product/1" route
│   └── [slug]    // "/product/abc" route
```

#### Key Files

1. **`page.tsx`**
- This file defines the content of a specific route.
- For example, the `page.tsx` file in the `about` folder will serve the `/about` route.

```tsx
// app/about/page.tsx
export default function AboutPage() {
  return <h1>About Us</h1>;
}
```

2. **`layout.tsx`**
- This file provides a shared layout for the pages in the same directory.
- Layouts can include headers, footers, navigation bars, or any UI structure.

```tsx
// app/layout.tsx (Root layout for all pages)
export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en">
      <body>
        <header>Global Header</header>
        <main>{children}</main>
        <footer>Global Footer</footer>
      </body>
    </html>
  );
}
```

```tsx
// app/about/layout.tsx (Specific layout for the "about" route)
export default function AboutLayout({ children }: { children: React.ReactNode }) {
  return (
    <div>
      <aside>About Sidebar</aside>
      <main>{children}</main>
    </div>
  );
}
```


#### Navigation with `Link` Component

The `Link` component is used to navigate between routes without a full page reload. It’s optimized for client-side routing.

``` tsx
import Link from 'next/link';

export default function Navigation() {
  return (
    <nav>
      <ul>
        <li><Link href="/">Home</Link></li>
        <li><Link href="/about">About</Link></li>
        <li><Link href="/contact">Contact</Link></li>
      </ul>
    </nav>
  );
}
```

#### Dynamic Navigation: Mapping Nav Links

You can dynamically generate navigation links using a map function.

```tsx
import Link from 'next/link';

const links = [
  { href: '/', label: 'Home' },
  { href: '/about', label: 'About' },
  { href: '/contact', label: 'Contact' },
];

export default function Navigation() {
  return (
    <nav>
      <ul>
        {links.map((link) => (
          <li key={link.href}>
            <Link href={link.href}>{link.label}</Link>
          </li>
        ))}
      </ul>
    </nav>
  );
}
```

#### Using `usePathname` for Active Links

The `usePathname` hook helps you access the current route, which is useful for highlighting the active link.

```tsx
'use client';

import Link from 'next/link';
import { usePathname } from 'next/navigation';

const links = [
  { href: '/', label: 'Home' },
  { href: '/about', label: 'About' },
  { href: '/contact', label: 'Contact' },
];

export default function Navigation() {
  const pathname = usePathname();

  return (
    <nav>
      <ul>
        {links.map((link) => (
          <li key={link.href}>
            <Link href={link.href}>
              <a style={{ fontWeight: pathname === link.href ? 'bold' : 'normal' }}>
                {link.label}
              </a>
            </Link>
          </li>
        ))}
      </ul>
    </nav>
  );
}
```