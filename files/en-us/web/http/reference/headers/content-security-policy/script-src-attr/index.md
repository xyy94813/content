---
title: "Content-Security-Policy: script-src-attr directive"
short-title: script-src-attr
slug: Web/HTTP/Reference/Headers/Content-Security-Policy/script-src-attr
page-type: http-csp-directive
browser-compat: http.headers.Content-Security-Policy.script-src-attr
sidebar: http
---

The HTTP {{HTTPHeader("Content-Security-Policy")}} (CSP) **`script-src-attr`** directive specifies valid sources for JavaScript inline event handlers.

This directive only specifies valid sources for inline script event handlers like `onclick`.
It does not apply to other JavaScript sources that can trigger script execution, such as URLs loaded directly into {{HTMLElement("script")}} elements and [XSLT stylesheets](/en-US/docs/Web/XML/XSLT).
(Valid sources can be specified for all JavaScript script sources using {{CSP("script-src")}}, or just for `<script>` elements using {{CSP("script-src-elem")}}.)

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">CSP version</th>
      <td>3</td>
    </tr>
    <tr>
      <th scope="row">Directive type</th>
      <td>{{Glossary("Fetch directive")}}</td>
    </tr>
    <tr>
      <th scope="row">{{CSP("default-src")}} fallback</th>
      <td>
        Yes.
        If this directive is absent, the user agent will look for the {{CSP("script-src")}} directive, and if both of them are absent, fallback to <code>default-src</code> directive.
      </td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Content-Security-Policy: script-src-attr 'none';
Content-Security-Policy: script-src-attr <source-expression-list>;
```

This directive may have one of the following values:

- `'none'`
  - : No resources of this type may be loaded. The single quotes are mandatory.
- `<source-expression-list>`
  - : A space-separated list of _source expression_ values. Resources of this type may be loaded if they match any of the given source expressions. For this directive, the following source expression values are applicable:
    - [`'unsafe-hashes'`](/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy#unsafe-hashes)
    - [`'unsafe-inline'`](/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy#unsafe-inline)
    - [`'report-sample'`](/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy#report-sample)

`script-src-attr` can be used in conjunction with {{CSP("script-src")}}, and will override that directive for checks on inline handlers:

```http
Content-Security-Policy: script-src <source>;
Content-Security-Policy: script-src-attr <source>;
```

## Examples

### Violation case

Given this CSP header:

```http
Content-Security-Policy: script-src-attr 'none'
```

…the following inline event handler is blocked and won't be loaded or executed:

```html
<button id="btn" onclick="doSomething()"></button>
```

Note that generally you should replace inline event handlers with {{domxref("EventTarget.addEventListener", "addEventListener")}} calls:

```js
document.getElementById("btn").addEventListener("click", doSomething);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{HTTPHeader("Content-Security-Policy")}}
- {{HTMLElement("script")}}
- {{CSP("script-src")}}
- {{CSP("script-src-elem")}}
