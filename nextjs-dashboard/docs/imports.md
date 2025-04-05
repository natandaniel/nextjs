# JavaScript/TypeScript Import Syntax

This guide explains the different import syntax patterns in JavaScript and TypeScript, with a focus on how they're used in Next.js applications.


## Overview

JavaScript and TypeScript provide different ways to import modules, each with its own syntax and use cases. Understanding these patterns is essential for working effectively with modern JavaScript frameworks like Next.js.

## Named Imports

Named imports use curly braces `{ }` to import specific exports from a module.

```typescript
import { lusitana } from "@/app/ui/fonts";
```

### Characteristics:

- Uses curly braces `{ }`
- Imports specific named exports
- Can import multiple exports in one statement
- Must match the exact name of the export (unless renamed)

### Example from Next.js:

```typescript
// fonts.ts
export const inter = Inter({ subsets: ["latin"] });
export const lusitana = Lusitana({
  weight: ["400", "700"],
  subsets: ["latin"],
});

// page.tsx
import { lusitana } from "@/app/ui/fonts";
```

## Default Imports

Default imports don't use curly braces and import the default export from a module.

```typescript
import Image from "next/image";
```

### Characteristics:

- No curly braces
- Imports the default export
- Can be renamed to any name
- Only one default export per import statement

### Example from Next.js:

```typescript
// next/image (simplified)
export default function Image({ src, alt, ...props }) {
  // Component implementation
}

// page.tsx
import Image from "next/image";
```

## Mixed Imports

You can combine named and default imports in a single statement.

```typescript
import Image, { StaticImageData } from "next/image";
```

### Example:

```typescript
// Import both default and named exports
import Link, { LinkProps } from "next/link";
```

## Import Aliases

You can rename imports using the `as` keyword.

```typescript
// Renaming a named import
import { lusitana as customFont } from "@/app/ui/fonts";

// Renaming a default import
import Image as NextImage from "next/image";
```

## Path Aliases

Next.js supports path aliases to simplify imports.

```typescript
// Using @/ alias (points to project root)
import { lusitana } from "@/app/ui/fonts";

// Without alias (relative path)
import { lusitana } from "../../ui/fonts";
```

Path aliases are configured in `tsconfig.json` or `jsconfig.json`:

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```

## Best Practices

1. **Use named imports for multiple exports**

   - Makes it clear what you're importing
   - Enables better tree-shaking

2. **Use default imports for single-purpose modules**

   - Common for components or utility modules
   - Simplifies imports

3. **Use path aliases for cleaner imports**

   - Avoid long relative paths (`../../../`)
   - Makes imports more maintainable

4. **Be consistent with naming**

   - Use descriptive names
   - Follow project conventions

5. **Group imports by type**
   - External libraries first
   - Internal modules second
   - Types/interfaces last

## Example in Next.js

```typescript
// External libraries
import { useState, useEffect } from "react";
import Image from "next/image";
import Link from "next/link";

// Internal modules
import { lusitana } from "@/app/ui/fonts";
import { fetchData } from "@/app/lib/data";

// Types
import type { User } from "@/app/types";

export default function ProfilePage() {
  // Component implementation
}
```

## Additional Resources

- [MDN: import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [TypeScript: Modules](https://www.typescriptlang.org/docs/handbook/modules.html)
- [JavaScript Modules: A Beginner's Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
