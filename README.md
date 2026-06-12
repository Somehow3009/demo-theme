# Axon Demo Theme — Premium WordPress Classic Portfolio

A high-performance, security-focused WordPress Classic Theme designed to showcase clean code architecture, programmatically defined ACF configurations, PHP 8.x modern standards, and smooth vanilla frontend interactions.

---

## 🚀 Key Technical Highlights

This project is built from scratch without bloated page builders (such as Elementor or Divi) to ensure maximum speed, clean DOM output, and optimal SEO.

### 1. Modern PHP 8.x Standards & WP Lifecycle Hooks
*   **Strict Typing:** Every PHP file starts with `declare(strict_types=1);` and utilizes strict return type hinting (`void`, `array`, `string`, `WP_Query`) to ensure run-time safety and self-documenting code.
*   **Decoupled Architecture:** Logic is organized cleanly inside the `/inc` folder (`setup.php`, `helpers.php`, `post-types.php`, `acf-fields.php`), keeping `functions.php` lightweight and readable.
*   **Lifecycle Hook Alignment:** 
    *   Assets are enqueued properly via the `wp_enqueue_scripts` and `admin_enqueue_scripts` hooks.
    *   Rewrites are dynamically flushed only upon theme activation using `after_switch_theme`.
    *   Custom post types (`case_study`) and custom filters (`excerpt_length` set to 20 words, `excerpt_more`) are hooked cleanly.

### 2. Strong Advanced Custom Fields (ACF Pro) Integration
*   **Programmatic Field Definitions:** Field groups are declared in code (`inc/acf-fields.php`) and fully controlled under version control.
*   **ACF Pro Repeater with Smart Fallbacks:** If ACF Pro is active, it serves a user-friendly Repeater field for Services. If ACF Pro is missing, it dynamically falls back to an ACF Free Group field structure, ensuring the site never crashes.
*   **Output Security:** Every field retrieved via `get_field()` or `get_sub_field()` is strictly escaped before output (using `esc_html()`, `esc_url()`, and translation helpers) to prevent XSS vulnerabilities.
*   **ACF JSON Syncing:** Integrated filters for `acf/settings/save_json` and `acf/settings/load_json` to automatically sync database configurations.

### 3. Premium Frontend (Clean CSS3 & Vanilla ES6 JS)
*   **Performance First:** Completely free from heavy external CSS frameworks. Built with a bespoke vanilla CSS design system utilizing CSS Custom Properties (variables) for theme tokens.
*   **Smooth Micro-interactions:**
    *   **Sticky Header:** Sticky navigation that shifts dynamically (adds background shadow and changes border opacity) on scroll using high-performance passive event listeners.
    *   **Staggered Entrance Animations:** Service and Case Study cards animate gracefully into view using a custom ES6 script powered by the modern **Intersection Observer API**.
    *   **Fluid Layouts:** Uses CSS Grid and Flexbox with a mobile-first, fully responsive grid system.

---

## 📁 Folder Structure

```text
axon-demo-theme/
├── assets/
│   ├── css/
│   │   ├── admin.css           # Styling for WP Admin dashboard previews
│   │   └── main.css            # Bespoke design tokens, layouts, and animations
│   └── js/
│       └── main.js             # Sticky header logic & Intersection Observer entry animations
├── acf-json/                   # Automatic ACF JSON syncing directory
├── inc/
│   ├── acf-fields.php          # Programmatic ACF field groups with Pro/Free fallback
│   ├── admin-preview.php       # Live WP_Query layout preview inside the Page Editor
│   ├── demo-content.php        # Auto-seeds sample posts and settings on activation
│   ├── helpers.php             # Custom query wrappers, excerpt length filters, and normalizers
│   ├── post-types.php          # Custom CPT registrations (e.g. Case Studies)
│   └── setup.php               # Theme support definitions and asset enqueuing
├── template-parts/
│   ├── case-studies.php        # Section template displaying latest CPT posts
│   ├── content-case-study-card.php
│   ├── hero.php                # ACF-powered hero section
│   └── services.php            # ACF-powered services loop
├── front-page.php              # Static homepage entry template
├── functions.php               # Primary theme entry point
├── header.php                  # Header markups (standard SEO & viewport metadata)
├── footer.php                  # Footer markups and wp_footer() call
└── style.css                   # WordPress Theme declaration file
```

---

## 🛠️ How to Deploy and Review this Demo

You can easily run this demo locally or showcase it directly to stakeholders using the following methods:

### Method A: Local Setup
1. Zip the `axon-demo-theme` folder.
2. Upload it to your WordPress site under **Appearance > Themes > Add New > Upload Theme**.
3. Activate the theme.
4. **Auto-seeding:** The theme will automatically create a page named `Home` and a few custom `Case Studies`, configure your reading settings, and map the homepage fields. 
5. Install the ACF (Free or Pro) plugin. Navigate to the Home page editor to update content.

### Method B: Sharing LocalWP using Live Links (Recommended for Recruiter Reviews)
If you are using **Local WP** (Local by Flywheel) to run this site locally, you can expose your site to the web with one click:
1. Open the **Local WP** dashboard.
2. Select the `themedemo` site.
3. Look at the bottom of the window for the **Live Links** option.
4. Click **Enable**.
5. Copy the generated public URL (e.g., `lean-plant.localsite.io`) and share it with your recruiter or attach it to your portfolio.
   * *Tip:* Live Links are password-protected by default. Make sure to provide the recruiter with the username and password listed next to the link in Local WP!

### Method C: Record a Technical Walkthrough (Highly Recommended)
Recruiters love concise, technical demonstrations. Since you possess excellent English communication skills:
1. Use a tool like **Loom**, **OBS Studio**, or **Vidyard** to record a quick 2-minute video.
2. Start by showing the beautiful frontend responsive layouts and scroll animations.
3. Go to the WP Admin editor and change the hero text via ACF to show how clients easily manage content.
4. Briefly open VS Code to showcase the `inc/` architecture, strict return types, and safety escaping logic.
5. Upload this video and share the link. It acts as an instant validation of your communication and engineering competence.
