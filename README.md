# Redirect

A theme that generates full-site redirection pages for migration from domain A to domain B.

## What is this

This theme is used when:

1. You have a site that is host at `foo.com`
2. And you want to migrate it to `bar.com`
3. The whole site's structure is not changed
4. You want users who visit `foo.com/*` to be automatically redirected to `bar.com/*`
5. You want search engine bots to reindex you site without losing position

## How does this work

This theme generates pages that contain nothing but 2 tags in `<head>` section:

```html
<meta http-equiv="refresh" content="0; url=http://new.domain.com/same/relative/url/of/old/site/">
<link rel="canonical" href="http://new.domain.com/same/relative/url/of/old/site/" />
```

The first tag redirects visitor to the new site. The second one tells search engine's bots how to reindex your site.


## How to use

* Make a full copy of your hexo site project.
* In the copied project folder, install this theme:

```shell
$ git clone https://github.com/akfish/hexo-theme-redirect.git themes/redirect
```

* Modify `theme` setting in copied site's `_config.yml` to `redirect`.
* Config new domain in copied site's `_config.yml` (without `http://` or `https://`):

```yaml
new_domain: new.domain.com
```

* Deploy copied site to your old domain.
* Deploy orignal site to `new.domain.com`

That's all.
