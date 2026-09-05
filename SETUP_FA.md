# راهنمای خیلی ساده برای موبایل

### اول Supabase
- وارد Supabase شوید و New project بزنید.
- بعد از ساخته‌شدن پروژه، SQL Editor > New query را بزنید.
- فایل `sql/schema.sql` را باز کنید، همه متن را کپی کنید و Run بزنید.
- از Authentication > Users یک مدیر بسازید.
- UUID کاربر را کپی کنید و در SQL اجرا کنید:
`insert into public.admin_users(user_id) values('UUID-اینجا');`
- Settings > API Keys، URL و Publishable Key را بردارید.
- فایل `config.js` را باز کنید و دو مقدار را جایگزین کنید.

### بعد Cloudflare Pages
- در GitHub یک repository بسازید.
- محتویات این پوشه را داخل repository بگذارید.
- در Cloudflare Pages همان repository را انتخاب کنید.
- Build command = `exit 0`
- Build output directory = `/`
- Deploy را بزنید.

آدرس رایگان سایت چیزی مثل `amlak-asghari.pages.dev` خواهد بود.
