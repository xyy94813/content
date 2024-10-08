---
title: "TextTrack: sourceBuffer property"
short-title: sourceBuffer
slug: Web/API/TextTrack/sourceBuffer
page-type: web-api-instance-property
browser-compat: api.TextTrack.sourceBuffer
---

{{APIRef("Media Source Extensions")}}

The read-only **`sourceBuffer`** property of the {{domxref("TextTrack")}} interface returns the
{{domxref("SourceBuffer")}} that created the track, or null if the track was not
created by a {{domxref("SourceBuffer")}} or the {{domxref("SourceBuffer")}} has been
removed from the {{domxref("MediaSource.sourceBuffers")}} attribute of its parent
media source.

## Value

A {{domxref("SourceBuffer")}} or null.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
