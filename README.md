# Zola Resume

[Chinese Version](README.CN.md)

Redesigned form [hugo resume](https://github.com/eddiewebb/hugo-resume).

## Features
+ This is basically a single-page website with auto-scrolling based on left-hand nav.
+ Dedicated project/publications pages allow more detail.
+ Includes a client-side search at '/search'.
+ Includes an `/admin` endpoint that can allow authorized users to use a WYSIWYG editor and commit files back to markdown, but with a Wordpress/CMS like experience.
+ Multilingual support out of the box (English by default, French translation included). UI strings come from `[languages.<lang>.translations]` in `config.toml`; translated content is provided as `_index.<lang>.md` / `<page>.<lang>.md`, and translated data files as `data/<file>.<lang>.json` (with fallback to the default-language file when missing).

## Quick Start

```bash
git clone git@github.com:alongwy/zola-resume.git
cd zola-resume
zola serve
# open http://127.0.0.1:1111/
```

## Installation
Just earlier we showed you how to run the theme directly. Now we start to install the theme in an existing site step by step.

### Step 1: Create a new zola site

```bash
zola init mysite
```

### Step 2: Install zola-resume
Download this theme to your themes directory:

```bash
cd mysite/themes
git clone git@github.com:alongwy/zola-resume.git
```

Or install as a submodule:

```bash
cd mysite
git init  # if your project is a git repository already, ignore this command
git submodule add git@github.com:alongwy/zola-resume.git themes/zola-resume
```

### Step 3: Configuration
Enable the theme in your config.toml in the site derectory:

```toml
theme = "zola-resume"
```

Or copy the config.toml.example from the theme directory to your project's root directory:

```bash
cp themes/zola-resume/config.toml.example config.toml
```

#### For CMS

```bash
cp themes/zola-resume/static/admin/config.yml static/admin/config.yml
```

and change those

```yaml
# static/admin/config.yml

backend:
  name: github
  repo: USERNAME/REPO
  branch: BRANCH
  cms_label_prefix: netlify-cms/
  site_domain: DOMAIN.netlify.com
```

### Step 4: Add new content
The theme ships an `content.example/` directory with the minimal section
skeleton expected by the templates (`_index.md` for `/`, `projects/`,
`opensource/`, `publications/`, `blog/`, plus the `search.md` page) in both
English and French. Copy it as a starting point, along with the data files:

```
cp -r themes/zola-resume/data .
cp -r themes/zola-resume/content.example content
```

Then customise: edit `content/_index.md` for your bio, drop new posts under
`content/projects/`, `content/blog/`, etc.

If you don't need a section, set `show_<name> = false` under `[extra]` in
`config.toml` and the matching `content/<name>/` directory becomes optional.

### Translations
Every `trans()` key the theme uses is listed in `config.toml.example` under
`[languages.en.translations]` (and `[languages.fr.translations]` for the
shipped French translation). Keep these blocks in your `config.toml` and
adjust the values to your liking. To add another language, copy one of the
blocks and translate the values; Zola will fail the build if a key is
missing.

### Step 5: Run the project
Just run zola serve in the root path of the project:

```
zola serve
```

This will start the Zola development web server accessible by default at http://127.0.0.1:1111. Saved changes will live reload in the browser.

## Examples

![screenshot](https://raw.githubusercontent.com/alongwy/zola-resume/master/screenshot.png)

See [along's site](https://resume.alongwy.top) for a live example.

## Setup & Use

This theme uses a combination of custom sections and some data files to drive content.

### Summary
Edit the main `contents/_index.md with a brief bio/summary`

### Data files
Data files are used for simple content presented on the homepage.

- [data/certifications.json](https://github.com/AlongWY/zola-resume/blob/main/data/certifications.json)
- [data/social.json](https://github.com/AlongWY/zola-resume/blob/main/data/social.json)
- [data/skills.json](https://github.com/AlongWY/zola-resume/blob/main/data/skills.json)
- [data/experience.json](https://github.com/AlongWY/zola-resume/blob/main/data/experience.json)
- [data/education.json](https://github.com/AlongWY/zola-resume/blob/main/data/education.json)

For each translated language, you can drop a parallel file (e.g. `data/experience.fr.json`); the templates load the language-specific file when present and fall back to the default one otherwise.

#### Experience missions

Each entry in `data/experience.json` accepts two optional rich-content fields:

- `summary` — a one-line description rendered as inline markdown (links, emphasis…). Block-level constructs like lists are not supported here.
- `missions` — a structured list of bullets, supporting up to 3 levels of nesting.

Both can be combined; either one can be omitted.

Each entry in `missions` is either:

- a plain string, rendered as a simple bullet (inline markdown allowed)
- an object `{ "text": "…", "items": [ … ] }` where `items` is another such array of strings/objects

```json
{
  "role": "DevOps Freelance",
  "company": "Independent",
  "range": "Since 04/2024",
  "missions": [
    {
      "text": "Built a fully Infrastructure-as-Code stack:",
      "items": [
        "Quarkus applications on OVH-managed Kubernetes",
        "Infrastructure with Terraform",
        "Cluster configuration with Ansible",
        "Observability stack"
      ]
    },
    "*Tooling:* Ansible, Terraform, Kubernetes, Helm, Grafana."
  ]
}
```

#### Skill levels

Each entry in `data/skills.json` accepts an optional `level` (integer 0–100). When set, the skill is rendered on its own row with a horizontal progress bar instead of the inline icon+name pill. Mix and match within a group as needed:

```json
{
  "grouping": "Infrastructure as Code",
  "skills": [
    { "name": "Ansible", "icon": "ansible", "level": 95 },
    { "name": "Terraform", "icon": "terraform", "level": 50 },
    "Packer"
  ]
}
```

### Projects/Opensource

The difference indicates your role as originator or colaborator.

### Publications
Similar to projects, create them under `publications`. Include any papers, speaking engagements, articles, etc.

### Blog / Posts
Similar to posts, create them under `blog`. Include any thoughts, musiings, etc.
**This template does not support a `posts` folder**

### Template params

Almost All personal information outside the above details is captured by extra in [`config.toml`](https://github.com/AlongWY/zola-resume/blob/main/config.toml), or can be edited in the "Settings" collection if using CMS.

## CMS Editor with Netlify CMS
**Does not require deployment to Netlify!**

[Netlify CMS](https://www.netlifycms.org/) is an open source project that enables CMS like experience for static site generation tools like Hugo. This theme includes a fully working integration and guide in [static/admin](https://github.com/AlongWY/zola-resume/tree/main/static/admin)

## Credits

This project ports the Hugo Resume theme by Feng Yunlong to support zola.

