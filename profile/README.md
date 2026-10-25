<h1 align="center">Your Django stack, fluent in every language.</h1>

<p align="center">
  One translation layer for <b>django CMS</b>, <b>Wagtail</b>, <b>django-parler</b> and
  <b>django-modeltranslation</b>, with one glossary, one translation memory and nothing
  published without an editor's decision.
</p>

<p align="center">
  <a href="https://ponyglot.app/#waitlist"><b>Join early access →</b></a>
  &nbsp;·&nbsp; <a href="https://ponyglot.app">ponyglot.app</a>
  &nbsp;·&nbsp; <a href="https://docs.ponyglot.app">Documentation</a>
</p>

---

An "AI translate" button is free in every CMS. Keeping a multilingual site **consistent,
current and reviewed** over months and languages is not. That's what Ponyglot does:

- 🧭 **Consistency.** One glossary and one translation memory across CMS pages and app models:
  a term is translated the same way everywhere, in every language.
- 🔄 **Currency.** Delta sync tracks every source sentence. When a page changes, you see which
  sentences are stale in which language, and only those are retranslated.
- ✅ **Control.** CMS content arrives as drafts, model content as suggestions with a diff.
  Editors approve; nothing goes live on its own.
- 🧩 **Coverage.** django CMS, Wagtail, django-parler and django-modeltranslation in one
  product, hosted in the EU.

## Packages

Open source (BSD-3-Clause). Install the core plus the connector for your stack:

| Package | For | Install |
|---|---|---|
| [**ponyglot**](https://pypi.org/project/ponyglot/)<br>[![PyPI](https://img.shields.io/pypi/v/ponyglot)](https://pypi.org/project/ponyglot/) | Core: sync, review admin, and the **django-parler** / **django-modeltranslation** adapters | `pip install "ponyglot[parler]"`<br>or `"ponyglot[modeltranslation]"` |
| [**djangocms-ponyglot**](https://github.com/ponyglot/djangocms-ponyglot)<br>[![PyPI](https://img.shields.io/pypi/v/djangocms-ponyglot)](https://pypi.org/project/djangocms-ponyglot/) | **django CMS 5**: pages, plugins, posts and your own models, as djangocms-versioning drafts | `pip install "djangocms-ponyglot[versioning]"` |
| **wagtail-ponyglot** | **Wagtail 7 / 8**: pages and snippets through wagtail-localize, as draft revisions | *coming soon* |

Python 3.10+, Django 5.2+. Then add your site's API key:

```python
# settings.py
import os

INSTALLED_APPS += [
    "ponyglot",
    "djangocms_ponyglot",           # django CMS sites
    "ponyglot.contrib.parler",      # or "ponyglot.contrib.modeltranslation"
]
PONYGLOT = {
    "API_KEY": os.environ["PONYGLOT_API_KEY"],
    "SOURCE_LANGUAGE": "en",
}
```

```sh
python manage.py migrate
python manage.py ponyglot check      # connects to your site in Ponyglot
python manage.py ponyglot backfill   # sends existing content once
```

The dashboard at [ponyglot.app](https://ponyglot.app) shows the same steps, tailored to your
stack, with your key filled in.

## Early access

Ponyglot is in early access: pilots get a discount for the first three months.
**[Join early access at ponyglot.app →](https://ponyglot.app/#waitlist)**
