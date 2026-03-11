# Singo Sansar Website — Editing Guide

This guide will walk you through how to update the website with your own photos, text, and contact email. You do not need any coding experience. All editing is done inside a single file called **`index.html`**.

---

## Before You Begin: Opening the File

1. Find the file called `index.html` in the project folder.
2. To **preview the website** in a browser, simply double-click `index.html`. It will open in your default browser (Chrome, Safari, Firefox, etc.).
3. To **edit the website**, you need to open `index.html` in a text editor. On Windows, you can right-click the file and choose **Open with → Notepad**. On Mac, right-click and choose **Open with → TextEdit**. A free, better option for both is **[Visual Studio Code](https://code.visualstudio.com/)** — it color-codes the text to make editing easier.
4. After making any change, **save the file** (Ctrl+S on Windows, Cmd+S on Mac), then **refresh the browser** to see your update.

---

## 1. Swapping Out Photos

Photos are stored in the **`photos/`** folder inside the project. To add or replace a photo:

1. Copy your new image file into the `photos/` folder.
2. Make sure the file name has no special characters. Spaces are okay (e.g. `My Photo.jpg`).

### Hero (the large background image at the very top)

In `index.html`, use **Find** (Ctrl+F or Cmd+F) and search for:

```text
Residential Women.jpg
```

You will find a line that looks like this:

```text
url('photos/Residential Women.jpg') center/cover no-repeat;
```

Replace `Residential Women.jpg` with the name of your new photo. For example:

```text
url('photos/My New Hero Photo.jpg') center/cover no-repeat;
```

---

### "Who We Are" section photo (the image beside the description)

Search for:

```text
Women in Community.jpg
```

You will find:

```html
<img src="photos/Women in Community.jpg" alt="Women in community">
```

Replace `Women in Community.jpg` with your photo's file name. You can also update the `alt="..."` text to briefly describe your photo — this helps with accessibility.

---

### Gallery slider photos

The gallery currently has six photos. Search for `gallery-item` to find them. Each one looks like this:

```html
<div class="gallery-item"><img src="photos/Daily Life in Bhaktapur.jpg" alt="Daily life in Bhaktapur"></div>
```

Replace the file name inside `src="photos/..."` with your photo's name. Also update the `alt="..."` description. To **add more photos**, copy one of these lines and paste it right below the last `</div>` in the gallery, then update the file name.

---

### Program card background photos

Each of the four "What We Do" cards has a faint photo behind it. Search for `program-card` and you will find lines like:

```text
url('photos/Women Tying Bundles of Dry Grass.jpg')
```

Replace each file name with your chosen photo, one per card.

---

## 2. Changing the Text

All the words on the website live in `index.html`. Use Find (Ctrl+F or Cmd+F) to locate the text you want to change, then simply type over it.

### Page title (shown in the browser tab)

Search for:

```text
Singo Sansar — Empowering Women in Sarlahi
```

Replace it with your own title.

---

### Hero section (the large text over the main photo)

Search for:

```text
Building Futures for
```

You will find:

```html
<h1>Building Futures for <em>Women</em> in Sarlahi</h1>
```

Edit the text between the tags. The word wrapped in `<em>...</em>` is displayed in gold — you can change that word too.

The smaller text below the heading is:

```html
<p>Through skills training, financial education, and community support...
```

Edit the text between `<p>` and `</p>`.

---

### "Who We Are" section

Search for:

```text
Rooted in Sarlahi. Growing Together.
```

Edit the heading and the paragraph text below it. Do not remove the `<br><br>` — that just adds spacing between paragraphs.

---

### "What We Do" cards

Search for each card title to find it:

- `Vocational Skills Training`
- `Financial Literacy`
- `Community Mentorship`
- `Education Support`

Each card looks like this:

```html
<h3>Vocational Skills Training</h3>
<p>Hands-on workshops in tailoring, handicrafts, food processing...</p>
```

Edit the `<h3>` for the card title and the `<p>` for the description.

---

### "Get In Touch" section

Search for:

```text
Connect With Singo Sansar
```

Edit the heading and the sentence below it to say whatever you like.

---

### Footer

Search for:

```text
Singo Sansar — Sarlahi, Nepal
```

Update the organization name, location, or the tagline on the line below.

---

## 3. Changing the Contact Email

Search for:

```text
mailto:info@singosansar.org
```

You will find:

```html
<a href="mailto:info@singosansar.org?subject=Getting%20in%20Touch" class="contact-mailto">
```

Replace `info@singosansar.org` with your real email address. Leave everything else on that line exactly as it is.

You can also change the subject line that pre-fills when someone clicks the button. Find `Getting%20in%20Touch` and replace it with your preferred subject — use `%20` in place of any spaces (e.g. `Hello%20from%20the%20Website`).

---

## Quick Reference

| What you want to change | Search for this in index.html |
| --- | --- |
| Hero background photo | `Residential Women.jpg` |
| About section photo | `Women in Community.jpg` |
| Gallery photos | `gallery-item` |
| Program card photos | `program-card` |
| Browser tab title | `Singo Sansar — Empowering` |
| Main heading | `Building Futures for` |
| About text | `Rooted in Sarlahi` |
| Card titles & text | `Vocational Skills Training` |
| Contact section text | `Connect With Singo Sansar` |
| Email address | `mailto:info@singosansar.org` |
| Footer text | `Singo Sansar — Sarlahi` |

---

## Tips

- **Always save** `index.html` after making changes, then **refresh** the browser to see them.
- If something looks broken, press **Ctrl+Z** (or Cmd+Z on Mac) to undo your last change.
- Do not delete `<` or `>` characters or the words inside them (like `class=` or `src=`) — only change the visible text or file names.
- Photo file names are case-sensitive. `My Photo.jpg` and `my photo.jpg` are treated as different files, so make sure the name in `index.html` matches the file in the `photos/` folder exactly.
