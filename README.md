![](/docs/static/assets/banners/whg_newsupport.png)

Welcome to the **Whitehill Support documentation** repository.  
This repository contains the source content powering the public support site:  
> https://support.whitehill.group/

---

![](/docs/static/assets/headbanners/whg_fork_nologo.png)

---

![](/docs/static/assets/banners/whg_guidelines.png)

Under `/sources`, you'll find pre-made **GIMP project files** for all three banner types used across the documentation. These ensure visual consistency throughout the site.

Each documentation category (Installation, Configuration, Updating, etc.) follows an established structure.  
When contributing, **please adhere to the existing format** to maintain clarity and consistency.

If no format exists yet, you're welcome to innovate, just make sure the following rules are respected:

### Required page structure

- An injected **YAML front matter header** containing:
    - `icon` _(see [Octicons](https://primer.github.io/octicons/) for reference)_
    - `label`
    - `order` _(controls sidebar and navigation ordering)_
    - `tags`
    - `image` _(`/static/assets/whg_headbanner.png`)_
    - `authors`
    - `categories`
- A top-level **H1 page title** (`# Page Title`)
- A **header image banner** with a concise visual title _(see `/sources`)_
- A short, single-line **tagline** placed directly below the banner
- **Callout blocks** (`!!!`, `!!!warning`, `!!!info`, etc.) for critical, contextual, or time-sensitive information

#### Recommended patterns (when applicable)
- Step or section blocks using `===` for procedural guides (Installation, Updating, Configuration)
- Clear section separators (`---`) between major content areas

### Pull request reviews

To keep reviews focused, please **request reviews from the documentation maintainers**, not management.

**Primary maintainers:**
- [@everywhxn](https://github.com/everywhxn) ([@everywhxn](https://discord.com/users/1160943839591288893) on Discord) - Documentation, structure & assets,
- [@TheCakeChicken](https://github.com/TheCakeChicken) ([@thecakechicken](https://discord.com/users/343081377249493044) on Discord) - Overseeing & project management.

> Please avoid pinging management for PR reviews unless explicitly necessary.
