# نسخه رایگان آنلاین — مشاور املاک اصغری

این نسخه برای انتشار بدون هاست سنتی طراحی شده است: سایت استاتیک روی Cloudflare Pages و دیتابیس/ورود/Storage روی Supabase.

## 1) ساخت Supabase
1. در Supabase یک پروژه Free بسازید.
2. SQL Editor را باز کنید و کل `sql/schema.sql` را اجرا کنید.
3. Authentication > Users یک کاربر مدیر با ایمیل و رمز بسازید.
4. در SQL Editor شناسه همان کاربر را اضافه کنید:
   `insert into public.admin_users(user_id) values('UUID-USER');`
5. برای اینکه هر کسی نتواند حساب بسازد، در Authentication تنظیمات Signups را غیرفعال کنید.
6. Settings > API Keys، Project URL و Publishable key را بردارید و داخل `config.js` بگذارید.

## 2) فعال‌سازی ۲ مرحله‌ای
پس از ورود مدیر، از پنل «راه‌اندازی ۲ مرحله‌ای» را بزنید و QR را با Google Authenticator / 1Password / Authy اسکن کنید. TOTP MFA در Supabase رایگان است.

## 3) Cloudflare Pages
این پوشه را در یک GitHub repository قرار دهید و آن را در Cloudflare Pages متصل کنید. Build command: `exit 0` و Build output directory: `/`.
سپس یک آدرس رایگان `*.pages.dev` خواهید داشت.

## 4) دامنه
فعلاً دامنه لازم نیست. بعداً از Pages > Custom domains می‌توان دامنه خریداری‌شده را وصل کرد.

## نکات امنیتی
- اطلاعات مالک در تابع عمومی نمایش داده نمی‌شود.
- جدول‌های حساس RLS دارند.
- کلید Publishable در سایت مجاز است؛ Secret/service_role را هرگز در فایل‌های سایت قرار ندهید.
- برای جلوگیری از هزینه ناخواسته، قبل از افزایش مصرف Storage، محدودیت‌های رایگان سرویس را بررسی کنید.
