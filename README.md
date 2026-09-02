# Sahaj Yoga Classes — website

## What's in here

    index.html          the whole site, one file (HTML + CSS + structured data)
    images/bharti.jpg   Bharti Chhajed portrait, 600x750
    images/vrushali.jpg Vrishali Kulkarni portrait, 600x750

Nothing else is needed. Open `index.html` in any browser to view it locally.

## Phone numbers

No phone number appears as text anywhere on the page, and there are no
`tel:` links. Contact runs entirely through the WhatsApp buttons.

One thing to be aware of: a WhatsApp deep link is `wa.me/<number>`, so the
number is inside the button's link even though nobody sees it on screen. It
shows in the browser status bar on hover and in "copy link address". There
is no way around that while still having a one-tap WhatsApp button. If you
want the numbers fully off the page, the alternative is a contact form,
which needs a backend and loses the one-tap behaviour.

## Fonts

The `<head>` loads two fonts from Google Fonts (Mukta and Tiro Devanagari
Marathi). If that ever fails to load, the page falls back to Nirmala UI /
Segoe UI, which still renders the Marathi and Hindi testimonials correctly.
Nothing breaks.

## Hosting it free

Domain: **sahajyogacentre.co.in** (already set in the canonical tag, the
Open Graph tags, the structured data, and the `CNAME` file).

GitHub Pages, in order:

1. Make a public repo. Upload `index.html`, `CNAME`, `README.md` and the
   `images` folder to the ROOT of the repo, not inside a subfolder.
2. Settings > Pages > Source: deploy from branch `main`, folder `/ (root)`.
   It goes live at `username.github.io/reponame` in a minute or two.
3. Settings > Pages > Custom domain: type `sahajyogacentre.co.in` and Save.
   Do this BEFORE touching DNS.
4. At the registrar, add four A records for the apex (host `@`):

       185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153

   and one CNAME record, host `www`, pointing at `username.github.io`.
   Delete any parking or default record the registrar added.
5. Wait. DNS can take up to 24 hours, usually much less.
6. Back in Settings > Pages, tick **Enforce HTTPS** once the checkbox
   becomes available. If it stays greyed out for a day, remove the custom
   domain and re-add it to force the certificate to regenerate.

Cloudflare Pages and Netlify work the same way if you prefer those.

## Changing the colours

All six brand colours are CSS variables at the top of the `<style>` block,
sampled from the vinyl signboard:

    --teal   #106371   banner teal
    --lotus  #C3BE60   logo olive green
    --cream  #FFFBD6   callout boxes
    --pink   #F1E0EA   name strip

Change them there and the whole page follows.

## Swapping a photo

Keep the same filename and a 4:5 aspect ratio (600x750 is what's there now)
and it will drop straight in.
