# A Birthday Countdown 🎈

A single-page website that:
- Counts down live to your friend's birthday, showing **"Day N: Happy Birthday ABCD-ABCD"**
- Has ambient **fireworks, balloons, confetti, and floating hearts** the whole time
- Automatically switches to **"Happy Birthday to my Everything"** the instant the birthday begins
- Reveals a **hidden, typewriter-style letter** — either by tapping the name five times (before the birthday) or by tapping the **Hidden Surprise ❤** button that appears once the birthday starts
- Lets you swap in your own background photo whenever you like

It's a single file (`index.html`), so it's free and easy to host on **GitHub Pages**.

---

## 1. Customize it (all in one place)

Open `index.html` in any text editor and find the `CONFIG` block near the top of the `<script>` section, about two-thirds of the way down the file. Everything you'd want to change lives there:

```js
const CONFIG = {
  NAME: "ABCD-ABCD",                       // your friend's real name
  START_DATE: "2026-07-23T00:00:00",       // when "Day 1" should start
  BIRTHDAY: "2026-07-30T00:00:00",         // the exact moment it flips to "Happy Birthday"
  BACKGROUND_IMAGE_URL: "",                // main background photo
  LETTER_BACKGROUND_URL: "",               // background behind the hidden letter
  LETTER_TEXT: `My dearest ABCD-ABCD, ...` // the hidden letter itself
};
```

**Notes:**
- `BIRTHDAY` is set to `2026-07-30T00:00:00` — the very start (midnight) of July 30th, so the page flips over right as the day begins. Adjust the year if needed.
- Times are read in the visitor's **local browser time**. If you and your friend are in different time zones, the "midnight" they see will be their own local midnight, not yours. If you want it to be a specific time zone regardless of who's viewing, let me know and I can adjust it to a fixed time zone.

## 2. Add your own background photo

You don't need any code for this — just:

1. Create a folder next to `index.html` called `images`.
2. Put your photo in it, e.g. `images/us.jpg`.
3. In `CONFIG`, set:
   ```js
   BACKGROUND_IMAGE_URL: "images/us.jpg",
   ```
4. Same idea for the letter's background photo, using `LETTER_BACKGROUND_URL`.

You can change the photo any time — just replace the file (or point to a new one) and re-upload to GitHub. No other code changes needed.

If you leave these blank, the site uses a soft midnight-gradient background instead, so it still looks good with no photo at all.

## 3. Host it for free on GitHub Pages

1. Go to [github.com](https://github.com) and create a **new repository** (e.g. `friend-birthday`). Any name works. It can be public or private — GitHub Pages works with public repos on free accounts; if you want it private, you'll need GitHub's paid tier for Pages, so public is the easy free route. (Just don't put anything you don't want the friend accidentally seeing before the big day — the URL won't be listed anywhere, but it isn't password-protected either.)
2. Upload `index.html` (and your `images` folder, if you added one) to the repository:
   - Click **Add file → Upload files**, drag both in, and commit.
3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Under **Branch**, choose `main` (or `master`) and folder `/ (root)`, then **Save**.
6. Wait about a minute, then refresh — GitHub will show you a live URL like:
   ```
   https://yourusername.github.io/friend-birthday/
   ```
7. That's your live site. Send that link to your friend whenever you're ready.

## 4. Testing before the big day

To preview the "after birthday" version without waiting:
- Temporarily change `BIRTHDAY` in `CONFIG` to a few minutes in the future, save, and reload the page in your browser (just double-click `index.html` to open it locally — no server needed).
- Once you've checked it looks right, change `BIRTHDAY` back to the real date and re-upload to GitHub.

## 5. Updating later

Any time you want to change the photo, the letter, or the name, just edit `index.html` in the `CONFIG` block and re-upload it to the same GitHub repository (Add file → Upload files → overwrite). The live link stays exactly the same.

---

Enjoy 🎉
