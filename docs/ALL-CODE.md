# Complete CohbyLearn Code - Copy & Paste Guide

This file tells you EXACTLY which code from my first message goes into which file.

---

## 1. DATABASE MIGRATIONS

### File: `supabase/migrations/20231201000001_core_schema.sql`
**What to copy:** From my first message, copy the ENTIRE "Migration 001: Core Schema" section
**Starts with:** `-- Enable UUID extension`
**Ends with:** `CREATE TRIGGER update_quiz_attempts_updated_at...`

### File: `supabase/migrations/20231201000002_functions.sql`
**What to copy:** From my first message, copy the ENTIRE "Migration 002: Helper Functions" section
**Starts with:** `-- Get current user's tenant ID`
**Ends with:** `$$ LANGUAGE plpgsql STABLE;`

### File: `supabase/migrations/20231201000003_rls_policies.sql`
**What to copy:** From my first message, copy the ENTIRE "Migration 003: Row-Level Security Policies" section  
**Starts with:** `-- Enable RLS on all tables`
**Ends with:** `USING (current_user_role() IN ('ORG_ADMIN', 'LEARNING_MANAGER'));`

---

## 2. TYPESCRIPT TYPES

### File: `lib/database.types.ts`
**What to copy:** From my first message, the entire Database types section
**Starts with:** `export type UserRole =`
**Ends with:** `};`

### File: `lib/supabase/client.ts`
**What to copy:** Browser client code
**Full code:**
```typescript
import { createBrowserClient } from '@supabase/ssr';
import { Database } from '@/lib/database.types';

export function createClient() {
  return createBrowserClient<Database>(
    process.env.NEXT_PUBLIC_SUPABASE_URL!,
    process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY!
  );
}
```

### File: `lib/supabase/server.ts`
**What to copy:** Server client code from my first message
**Starts with:** `import { createServerClient`
**Ends with:** `});`

---

## 3. SERVICE LAYER

### File: `lib/services/tenant.service.ts`
**What to copy:** Complete TenantService class from my first message
**Starts with:** `import { SupabaseClient }`
**Ends with:** `}`

### File: `lib/services/user.service.ts`  
**What to copy:** Complete UserService class

### File: `lib/services/course.service.ts`
**What to copy:** Complete CourseService class

### File: `lib/services/enrolment.service.ts`
**What to copy:** Complete EnrolmentService class

### File: `lib/services/report.service.ts`
**What to copy:** Complete ReportService class

---

## 4. CONFIGURATION FILES (ALREADY ON GITHUB ✅)

- ✅ package.json
- ✅ .env.example  
- ✅ README.md
- ✅ LICENSE
- ✅ .gitignore

---

## 5. ADDITIONAL CONFIG FILES NEEDED

### File: `tsconfig.json`
```json
{
  "compilerOptions": {
    "target": "ES2017",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "bundler",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true,
    "plugins": [
      {
        "name": "next"
      }
    ],
    "paths": {
      "@/*": ["./*"]
    }
  },
  "include": ["next-env.d.ts", "**/*.ts", "**/*.tsx", ".next/types/**/*.ts"],
  "exclude": ["node_modules"]
}
```

### File: `next.config.js`
```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {}

module.exports = nextConfig
```

### File: `tailwind.config.ts`
```typescript
import type { Config } from "tailwindcss";

const config: Config = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
export default config;
```

### File: `postcss.config.js`
```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

---

## HOW TO USE THIS FILE:

1. Open my FIRST message (scroll to the very top of this conversation)
2. Find each section I mention above
3. Copy the EXACT code from that section
4. Create the file with the exact name I gave you
5. Paste the code into that file

## EXAMPLE:
For `supabase/migrations/20231201000001_core_schema.sql`:
- Go to my first message
- Find the heading "### Migration 001: Core Schema"
- Copy EVERYTHING from `-- Enable UUID extension` down to the last trigger
- Create file `supabase/migrations/20231201000001_core_schema.sql`
- Paste it in

Repeat for every file listed above!
