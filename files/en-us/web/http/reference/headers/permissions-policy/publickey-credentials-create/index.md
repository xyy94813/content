---
title: "Permissions-Policy: publickey-credentials-create directive"
short-title: publickey-credentials-create
slug: Web/HTTP/Reference/Headers/Permissions-Policy/publickey-credentials-create
page-type: http-permissions-policy-directive
status:
  - experimental
browser-compat: http.headers.Permissions-Policy.publickey-credentials-create
sidebar: http
---

{{SeeCompatTable}}

The HTTP {{HTTPHeader("Permissions-Policy")}} header `publickey-credentials-create` directive controls whether the current document is allowed to use the [Web Authentication API](/en-US/docs/Web/API/Web_Authentication_API) to create new WebAuthn credentials, i.e., via {{domxref("CredentialsContainer.create","navigator.credentials.create({publicKey})")}}.

Specifically, where a defined policy blocks use of this feature, the {{jsxref("Promise")}} returned by `navigator.credentials.create({publicKey})` will reject with a `NotAllowedError` {{domxref("DOMException")}}.
If the method is called cross-origin, the {{jsxref("Promise")}} will also reject with a `NotAllowedError` if the feature is granted by [`allow=` on an iframe](/en-US/docs/Web/HTTP/Reference/Headers/Permissions-Policy#iframes) and the frame does not also have {{glossary("Transient activation")}}.

## Syntax

```http
Permissions-Policy: publickey-credentials-create=<allowlist>;
```

- `<allowlist>`
  - : A list of origins for which permission is granted to use the feature. See [`Permissions-Policy` > Syntax](/en-US/docs/Web/HTTP/Reference/Headers/Permissions-Policy#syntax) for more details.

## Default policy

The default allowlist for `publickey-credentials-create` is `self`.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{HTTPHeader("Permissions-Policy")}} header
- [Permissions Policy](/en-US/docs/Web/HTTP/Guides/Permissions_Policy)
- [Web Authentication API](/en-US/docs/Web/API/Web_Authentication_API)
- {{DOMxRef("PublicKeyCredential")}} interface
