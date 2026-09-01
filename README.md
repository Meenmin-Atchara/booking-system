# ระบบจองคิว (Booking System)

ระบบรับจองคิวออนไลน์ พร้อมตรวจสอบความซ้ำซ้อนอัตโนมัติ
และหน้าจัดการหลังบ้านสำหรับร้าน

## Tech Stack

- **Next.js 15** (App Router) + TypeScript
- **PostgreSQL** + Prisma ORM
- **Auth.js v5** — ระบบล็อกอินและสิทธิ์ผู้ใช้
- **Tailwind CSS** + shadcn/ui
- **FullCalendar** — ปฏิทินคิว
- **Vitest** — unit test

## เริ่มใช้งาน

```bash
# 1. ติดตั้ง dependencies
pnpm install

# 2. คัดลอกและตั้งค่า environment
cp .env.example .env

# 3. เปิดฐานข้อมูล
docker compose up -d

# 4. สร้างตารางและข้อมูลตั้งต้น
pnpm prisma migrate dev
pnpm prisma db seed

# 5. รัน
pnpm dev
```

เปิด http://localhost:3000

**บัญชีทดสอบ:** `owner@shop.com` / `password123`

## คำสั่งที่ใช้บ่อย

| คำสั่ง | ทำอะไร |
|---|---|
| `pnpm dev` | รันโหมดพัฒนา |
| `pnpm test` | รัน unit test |
| `pnpm prisma studio` | เปิดหน้าดูฐานข้อมูล |
| `pnpm prisma migrate dev` | สร้าง migration ใหม่ |
| `pnpm build` | build สำหรับ production |

## โครงสร้างโปรเจกต์

```
src/
├── app/            # หน้าเว็บและ API routes
├── components/     # UI components
├── lib/            # ★ business logic (conflict engine อยู่นี่)
├── server/         # Server Actions
└── types/
prisma/             # schema และ migrations
```

## เอกสารเพิ่มเติม

- [เอกสารออกแบบระบบ](./docs/design.md)
- [คู่มือผู้ใช้](./docs/user-guide.md)
