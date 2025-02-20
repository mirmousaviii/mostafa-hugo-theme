# Mostafa Hugo Theme

Welcome to `mostafa-hugo-theme`! This is a flexible theme for Hugo.

The theme supports multiple languages, various content types, and integrates seamlessly with social media platforms.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
  - [Install via Hugo Modules (Recommended)](#install-via-hugo-modules-recommended)
    - [1.1 Initialize Hugo Modules](#11-initialize-hugo-modules-if-not-already-initialized)
    - [1.2 Add the theme as a module](#12-add-the-theme-as-a-module)
    - [1.3 Fetch the theme](#13-fetch-the-theme)
  - [Install via Git Submodule (Advanced Users)](#install-via-git-submodule-advanced-users)
    - [2.1 Add the theme as a submodule](#21-add-the-theme-as-a-submodule)
    - [2.2 Initialize and update the submodule](#22-initialize-and-update-the-submodule)
    - [2.3 Set the theme in `config.toml`](#23-set-the-theme-in-configtoml)
  - [Install via Manual Download (For Non-Git Users)](#install-via-manual-download-for-non-git-users)
    - [3.1 Download the theme](#31-download-the-theme)
    - [3.2 Set the theme in `config.toml`](#32-set-the-theme-in-configtoml)
- [Configuration](#configuration)
- [Sample Configurations](#sample-configurations)
- [Running Your Hugo Site](#running-your-hugo-site)
- [Contributing](#contributing)
- [License](#license)

## Features

- Lightweight and fast
- Responsive design
- Multilingual support
- Dark and modern theme
- Supports various content types (posts, pages, galleries, videos, etc.)
- Integrated with social media

## Installation

You can install `mostafa-hugo-theme` using different methods depending on your preference.

### Install via Hugo Modules (Recommended)

#### 1.1 Initialize Hugo Modules (if not already initialized)

Run this command inside your Hugo project:

```bash
hugo mod init github.com/yourusername/your-hugo-site
```

#### 1.2 Add the theme as a module

Edit your `config.toml` file and add:

```toml
[module]
    [[module.imports]]
        path = "github.com/mirmousaviii/mostafa-hugo-theme"
```

#### 1.3 Fetch the theme

Run:

```bash
hugo mod tidy
```

✅ Done! The theme is now installed, and Hugo will automatically pull updates when you run `hugo mod tidy`.

### Install via Git Submodule (Advanced Users)

#### 2.1 Add the theme as a submodule

Run:

```bash
git submodule add https://github.com/mirmousaviii/mostafa-hugo-theme.git themes/mostafa-hugo-theme
```

#### 2.2 Initialize and update the submodule

Run:

```bash
git submodule update --init --recursive
```

#### 2.3 Set the theme in `config.toml`

```toml
theme = "mostafa-hugo-theme"
```

✅ Now the theme is linked to your project as a submodule! To update it, use:

```bash
git submodule update --remote --merge
```

### Install via Manual Download (For Non-Git Users)

If you don’t use Git, you can download the theme manually.

#### 3.1 Download the theme

1. Go to [GitHub Repository](https://github.com/mirmousaviii/mostafa-hugo-theme).
2. Click on **"Code" → "Download ZIP"**.
3. Extract the ZIP file and place it inside your Hugo project under `themes/mostafa-hugo-theme/`.

#### 3.2 Set the theme in `config.toml`

```toml
theme = "mostafa-hugo-theme"
```

## Configuration

Here are the configuration options for the theme.

### Basic Settings

- `baseURL`: The website URL (https://mirmousavi.com/)
- `title`: Main site title
- `DefaultContentLanguage`: Default content language (en)
- `googleAnalytics`: Google Analytics tracking ID
- `enableRobotsTXT`: Enables generation of robots.txt file

### Site Parameters

#### Media & Design

- `resizeImages`: Automatically resizes and crops images
- `contentFont`: Main font for LTR content
- `contentRTLFont`: Font for RTL content (Vazirmatn)

#### Content Display

- `paginate`: Number of articles per page (10)
- `showReadingTime`: Displays estimated reading time for articles
- `tocMinWordCount`: Minimum word count to display Table of Contents (400)

#### SEO & Metadata

- `author`: Site author name
- `description`: Site description for SEO
- `keywords`: SEO keywords
- `subtitle`: Site subtitle

#### Social Media & Footer

- `socialMediaLinks`: Array of social media links with icons
  - GitHub
  - LinkedIn
  - Twitter
  - Email
- `otherLinks`: Additional footer links
  - Garmin Apps
  - Persian LUG
  - CoderConf
- `showFooter`: Controls footer visibility

### Multilingual Support

The site supports multiple languages:

- English (en-US)
- German (de-DE)
- Dutch (nl-NL)
- Persian (fa-IR)
- etc. (see './i18n/')

Each language can have its own:

- Title
- Subtitle
- Language direction (LTR/RTL)
- Weight (for ordering)

### Markdown Settings

- `defaultMarkdownHandler`: Uses goldmark
- `unsafe`: HTML rendering in markdown (disabled)
- Table of Contents configuration:
  - `startLevel`: 2
  - `endLevel`: 5
  - `ordered`: false

### Output Formats

- Home page: HTML, RSS, JSON
- Regular pages: HTML, RSS

## Sample Configurations

Here is asample configurations for the theme.

```toml
baseURL = 'https://mirmousavi.com/'
title = "Mostafa Mirmousavi"

# Change to one of your content languages defined at the end.
DefaultContentLanguage = "en"

# Enable / Disable Google Analytics statistics
googleAnalytics = "G-XXXXXXXXXX"

# Generate the robots.txt file for SEO
enableRobotsTXT = true

[module]
    [[module.imports]]
        path = "github.com/mirmousaviii/mostafa-hugo-theme"

[params]
    # Custom CSS / JS modules that will be imported by the template.
    # Files are relative to the static/ directory or a URL.
    # Files are imported in the order they appear here, after
    # theme.css and theme.js, respectively.
    css_modules = []
    js_modules = []

    # Description and meta data for the search engines
    author = "Mostafa Mirmousavi"
    description = "Software Engineer"
    keywords = "javascript, typescript, react, nodejs, monkeyc"
    subtitle = "A software engineer"


    # How many articles should be displayed at once?
    paginate = 10

    # Media configuration
    # let hugo automatically resize and crop your images to the correct sizes
    # NB: When enabled the image files get renamed by adding additional information,
    #     even if the image has the correct sizes.
    resizeImages = true


    # always display the top navigation when scrolling
    # works only with permanentTopNav = true
    #stickyNav = true


    # Style configuration
    #contentFont = "'Open Sans',sans-serif"
    #contentRTLFont = "Vazirmatn, sans-serif"

    #baseColor = "#191A19"
    #pageBackgroundColor = "$base-color"
    #specialColor = "#2D3642"
    #highlightColor = "#ffffff"
    #textColor = "#7a7a7a"

    #navBackgroundColor = "$special-color"
    #navTextColor = "$page-background-color"
    #algoliaSearchBoxColor = "#444"
    #algoliaSearchBoxIconColor = "#888"
    #algoliaSearchBoxBackgroundColor = "#fafafa"
    #algoliaBorderColor = "#e4e4e4"

    #headerTextColor = "#FF8D00"

    #logoColor = "darken($page-background-color, 1)"
    #bubbleColor = "$highlight-color"
    #bubbleBackgroundColor = "#ccc"
    #bubbleHoverColor = "$highlight-color"

    #articleBackgroundColor = "#343434"
    #metaTextColor = "#999999"
    #metaBorderColor = "#eeeeee"
    #continueReadingHoverColor = "$meta-text-color"

    #footerBackgroundColor = "$page-background-color"
    #footerHeadlineColor = "$highlight-color"


    # Content configuration
    # Enable an optional pinned page to display at the top of the index
    #pinnedPost = "/quote/routine/"
    # Set to true to pin only to the first page, false to all pages
    #pinOnlyToFirstPage = true

    # enable highlight.js for syntax highlighting or (if set to false) use
    # the hugo built-in chroma highlighter
    enableHighlightJs = true

    # enable automatic localization of the article's PublishedDate with momentjs
    enableMomentJs = false

    # customize the date format | only works if momentjs is disabled | only works with English month names
    # you can customize it with the options you find here:
    # https://gohugo.io/methods/time/format/
    dateFormat = "Monday, January 2, 2006" //default is 2006-01-02

    # display the estimated reading time for an article
    showReadingTime = true

    # Minimum word count to display the Table of Contents
    tocMinWordCount = 400

    # Footer configuration
    showFooter = true

    # How many articles should be displayed at latest posts in the footer?
    # Set to -1 to hide the 'Latest Posts' column
    amountLatestPostsInFooter = 7

    # How many categories should be displayed in the footer section?
    # Set to -1 to hide the 'Categories' column
    amountCategoriesInFooter = 7

    # define your links with FontAwesome 5 (only free icons are supported)
    # all icons https://fontawesome.com/icons?d=gallery&m=free
    # brand icons https://fontawesome.com/icons?d=gallery&s=brands&m=free
    socialMediaLinks = [
        { name = "GitHub", link = "https://github.com/mirmousaviii", icon = "fab fa-github"},
        { name = "Linkedin", link = "https://linkedin.com/in/mirmousavi/en", icon = "fab fa-linkedin" },
        { name = "Twitter / X", link = "https://twitter.com/mirmousaviii", icon = "fab fa-twitter" },
        { name = "RSS", link = "/index.xml", icon = "fas fa-rss" },
    ]

    # show other links in the footer
    otherLinks = [
        { name = "Garmin Apps", link = "https://apps.garmin.com/developer/763f08dc-2be1-402f-b9b3-f3861b4df947/apps"},
        { name = "Mirmousavi.com", link = "https://mirmousavi.com/"},
    ]

    # show an archive link in the footer
    #showArchive = true

    # archive grouping: "2006" by year, "2006-01" by month
    #archiveDateGrouping = "2006-01"

    # credits line configuration
    #copyrightUseCurrentYear = true  # set to true to always display the current year in the copyright
    #copyrightYearOverride = "2024"
    #copyrightBy = "by Mostafa Mirmousavi" # default is "by {site title}"
    #copyrightUrl = "https://mirmousavi.com" # default is .Site.BaseURL


# customize your available languages for your multi-lingual site
[Languages]
    [Languages.en]
        weight = 10
        languageCode = 'en-US'
        languageDirection = 'ltr'
        languageName = 'English'
        title = "Mostafa Mirmousavi"
        [Languages.en.params]
            subtitle = "Software Engineer"
    [Languages.de]
        weight = 20
        languageCode = 'de-DE'
        languageDirection = 'ltr'
        languageName = 'German'
        title = "Mostafa Mirmousavi"
        [Languages.de.params]
            subtitle = "Softwareentwickler"
    [Languages.nl]
        weight = 30
        languageCode = 'nl-NL'
        languageDirection = 'ltr'
        languageName = 'Dutch'
        title = "Mostafa Mirmousavi"
        [Languages.nl.params]
            subtitle = "Software Engineer"
    [Languages.fa]
        weight = 40
        languageCode = 'fa-IR'
        languageDirection = 'rtl'
        languageName = 'Persian'
        title = "مصطفی میرموسوی"
        [Languages.fa.params]
            subtitle = "برنامه نویس"
    

[markup]
    defaultMarkdownHandler = 'goldmark'
    [markup.goldmark]
    [markup.goldmark.renderer]
      # change to 'true' if you need to render raw HTML within your markdown content
      unsafe = false

    [markup.tableOfContents]
        endLevel = 5
        ordered = false
        startLevel = 2


# do NOT change anything below
[taxonomies]
    author   = "author"
    tag      = "tags"
    category = "categories"
    series   = "series"

[outputs]
    home = [ "HTML", "RSS", "JSON" ]
    page = [ "HTML", "RSS" ]
```

## Running Your Hugo Site

After installing the theme, run:

```bash
hugo server
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request on [GitHub](https://github.com/mirmousaviii/mostafa-hugo-theme).

## License

This theme is licensed under the MIT License. See the [LICENSE](https://github.com/mirmousaviii/mostafa-hugo-theme/blob/main/LICENSE) file for more information.
