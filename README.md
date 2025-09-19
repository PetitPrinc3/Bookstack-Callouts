# Bookstack-Callouts

![[]](./callouts.png)

## Usage 

In your Markdown editor, call your callouts by type :

```Mardown
> [!TYPE] Whatever optional title
> Some text or whatever markdown content
```

## Setup

To apply this theme, add the following to your BookStack's custom HTML head content under `Settings > Customization > Custom HTML Head Content` :

```html
<style>
  [data-callout] {
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
    padding: 1rem;
    padding-bottom: 1.25rem;
    border-radius: 0.5rem;
    border-width: 1px;
    border-color: rgba(37, 99, 235, 0.2);
    background-color: rgba(96, 165, 250, 0.2);
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  
  html.dark [data-callout] {
    border-color: rgba(30, 64, 175, 0.2);
    background-color: rgba(59, 130, 246, 0.1);
  }
  
  [data-callout] > [data-callout-title] {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 0.5rem;
    padding: 0;
    font-weight: 700;
    color: rgb(59, 130, 246);
  }
  
  [data-callout] > [data-callout-title]:not(:only-child) {
    margin-bottom: 0.5rem;
  }
  
  [data-callout] > [data-callout-title]:empty::after {
    content: "Note";
  }
  
  [data-callout] > [data-callout-title]::before {
    /*margin-top: 0.25rem;*/
    display: block;
    height: 1.25rem;
    width: 1.25rem;
    background-color: currentColor;
    content: "";
    mask-repeat: no-repeat;
    mask-size: cover;
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTE3IDNhMi44NSAyLjgzIDAgMSAxIDQgNEw3LjUgMjAuNUwyIDIybDEuNS01LjVabS0yIDJsNCA0Ii8+PC9zdmc+");
  }
  
  [data-callout] > [data-callout-body] {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  
  [data-callout] > [data-callout-body] > * {
    margin: 0;
  }
  
  details[data-callout] > summary[data-callout-title] {
    cursor: pointer;
  }
  
  details[data-callout] > summary[data-callout-title]::after {
    width: 100%;
    background-position: right;
    background-repeat: no-repeat;
    content: "";
    background-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzg4ODg4OCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Im05IDE4bDYtNmwtNi02Ii8+PC9zdmc+");
    background-size: 1.5rem;
  }
  
  details[data-callout] > summary[data-callout-title]:not(:empty)::after {
    margin-top: auto;
    margin-bottom: auto;
    margin-left: auto;
    height: 1.5rem;
    width: 1.5rem;
  }
  
  details[data-callout][open] > summary[data-callout-title]::after {
    background-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzg4ODg4OCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Im02IDlsNiA2bDYtNiIvPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="info"] {
    border-color: rgba(37, 99, 235, 0.2);
    background-color: rgba(96, 165, 250, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="info"] {
    border-color: rgba(30, 64, 175, 0.2);
    background-color: rgba(59, 130, 246, 0.1);
  }
  
  [data-callout][data-callout-type="info"] > [data-callout-title] {
    color: rgb(59, 130, 246);
  }
  
  [data-callout][data-callout-type="info"] > [data-callout-title]:empty::after {
    content: "Info";
  }
  
  [data-callout][data-callout-type="info"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTE3IDNhMi44NSAyLjgzIDAgMSAxIDQgNEw3LjUgMjAuNUwyIDIybDEuNS01LjVabS0yIDJsNCA0Ii8+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="todo"] {
    border-color: rgba(37, 99, 235, 0.2);
    background-color: rgba(96, 165, 250, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="todo"] {
    border-color: rgba(30, 64, 175, 0.2);
    background-color: rgba(59, 130, 246, 0.1);
  }
  
  [data-callout][data-callout-type="todo"] > [data-callout-title] {
    color: rgb(59, 130, 246);
  }
  
  [data-callout][data-callout-type="todo"] > [data-callout-title]:empty::after {
    content: "ToDo";
  }
  
  [data-callout][data-callout-type="todo"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxnIGZpbGw9Im5vbmUiIHN0cm9rZT0iIzg4ODg4OCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiPjxwYXRoIGQ9Ik0yMiAxMS4wOFYxMmExMCAxMCAwIDEgMS01LjkzLTkuMTQiLz48cGF0aCBkPSJtOSAxMWwzIDNMMjIgNCIvPjwvZz48L3N2Zz4=");
  }
  
  [data-callout][data-callout-type="abstract"],
  [data-callout][data-callout-type="summary"],
  [data-callout][data-callout-type="tldr"] {
    border-color: rgba(8, 145, 178, 0.2);
    background-color: rgba(45, 212, 191, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="abstract"],
  html.dark [data-callout][data-callout-type="summary"],
  html.dark [data-callout][data-callout-type="tldr"] {
    border-color: rgba(21, 94, 117, 0.2);
    background-color: rgba(20, 184, 166, 0.1);
  }
  
  [data-callout][data-callout-type="abstract"] > [data-callout-title],
  [data-callout][data-callout-type="summary"] > [data-callout-title],
  [data-callout][data-callout-type="tldr"] > [data-callout-title] {
    color: rgb(20, 184, 166);
  }
  
  [data-callout][data-callout-type="abstract"] > [data-callout-title]::before,
  [data-callout][data-callout-type="summary"] > [data-callout-title]::before,
  [data-callout][data-callout-type="tldr"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxnIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiI+PHJlY3Qgd2lkdGg9IjgiIGhlaWdodD0iNCIgeD0iOCIgeT0iMiIgcng9IjEiIHJ5PSIxIi8+PHBhdGggZD0iTTE2IDRoMmEyIDIgMCAwIDEgMiAydjE0YTIgMiAwIDAgMS0yIDJINmEyIDIgMCAwIDEtMi0yVjZhMiAyIDAgMCAxIDItMmgybTQgN2g0bS00IDVoNG0tOC01aC4wMU04IDE2aC4wMSIvPjwvZz4+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="abstract"] > [data-callout-title]:empty::after {
    content: "Abstract";
  }
  
  [data-callout][data-callout-type="summary"] > [data-callout-title]:empty::after {
    content: "Summary";
  }
  
  [data-callout][data-callout-type="tldr"] > [data-callout-title]:empty::after {
    content: "TL;DR";
  }
  
  [data-callout][data-callout-type="tip"],
  [data-callout][data-callout-type="hint"] {
    border-color: rgba(8, 145, 178, 0.2);
    background-color: rgba(45, 212, 191, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="tip"],
  html.dark [data-callout][data-callout-type="hint"] {
    border-color: rgba(21, 94, 117, 0.2);
    background-color: rgba(20, 184, 166, 0.1);
  }
  
  [data-callout][data-callout-type="tip"] > [data-callout-title],
  [data-callout][data-callout-type="hint"] > [data-callout-title] {
    color: rgb(20, 184, 166);
  }
  
  [data-callout][data-callout-type="tip"] > [data-callout-title]::before,
  [data-callout][data-callout-type="hint"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTguNSAxNC41QTIuNSAyLjUgMCAwIDAgMTEgMTJjMC0xLjM4LS41LTItMS0zYy0xLjA3Mi0yLjE0My0uMjI0LTQuMDU0IDItNmMuNSAyLjUgMiA0LjkgNCA2LjVjMiAxLjYgMyAzLjUgMyA1LjVhNyA3IDAgMSAxLTE0IDBjMC0xLjE1My40MzMtMi4yOTQgMS0zYTIuNSAyLjUgMCAwIDAgMi41IDIuNSIvPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="tip"] > [data-callout-title]:empty::after {
    content: "Tip";
  }
  
  [data-callout][data-callout-type="hint"] > [data-callout-title]:empty::after {
    content: "Hint";
  }
  
  [data-callout][data-callout-type="important"] {
    border-color: rgba(8, 145, 178, 0.2);
    background-color: rgba(45, 212, 191, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="important"] {
    border-color: rgba(21, 94, 117, 0.2);
    background-color: rgba(20, 184, 166, 0.1);
  }
  
  [data-callout][data-callout-type="important"] > [data-callout-title] {
    color: rgb(20, 184, 166);
  }
  
  [data-callout][data-callout-type="important"] > [data-callout-title]:empty::after {
    content: "Important";
  }
  
  [data-callout][data-callout-type="important"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTguNSAxNC41QTIuNSAyLjUgMCAwIDAgMTEgMTJjMC0xLjM4LS41LTItMS0zYy0xLjA3Mi0yLjE0My0uMjI0LTQuMDU0IDItNmMuNSAyLjUgMiA0LjkgNCA2LjVjMiAxLjYgMyAzLjUgMyA1LjVhNyA3IDAgMSAxLTE0IDBjMC0xLjE1My40MzMtMi4yOTQgMS0zYTIuNSAyLjUgMCAwIDAgMi41IDIuNSIvPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="success"],
  [data-callout][data-callout-type="check"],
  [data-callout][data-callout-type="done"] {
    border-color: rgba(22, 163, 74, 0.2);
    background-color: rgba(74, 222, 128, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="success"],
  html.dark [data-callout][data-callout-type="check"],
  html.dark [data-callout][data-callout-type="done"] {
    border-color: rgba(21, 128, 61, 0.2);
    background-color: rgba(34, 197, 94, 0.1);
  }
  
  [data-callout][data-callout-type="success"] > [data-callout-title],
  [data-callout][data-callout-type="check"] > [data-callout-title],
  [data-callout][data-callout-type="done"] > [data-callout-title] {
    color: rgb(34, 197, 94);
  }
  
  [data-callout][data-callout-type="success"] > [data-callout-title]::before,
  [data-callout][data-callout-type="check"] > [data-callout-title]::before,
  [data-callout][data-callout-type="done"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTIwIDZMOSAxN2wtNS01Ii8+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="success"] > [data-callout-title]:empty::after {
    content: "Success";
  }
  
  [data-callout][data-callout-type="check"] > [data-callout-title]:empty::after {
    content: "Check";
  }
  
  [data-callout][data-callout-type="done"] > [data-callout-title]:empty::after {
    content: "Done";
  }
  
  [data-callout][data-callout-type="question"],
  [data-callout][data-callout-type="help"],
  [data-callout][data-callout-type="faq"] {
    border-color: rgba(234, 88, 12, 0.2);
    background-color: rgba(251, 146, 60, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="question"],
  html.dark [data-callout][data-callout-type="help"],
  html.dark [data-callout][data-callout-type="faq"] {
    border-color: rgba(194, 65, 12, 0.2);
    background-color: rgba(249, 115, 22, 0.1);
  }
  
  [data-callout][data-callout-type="question"] > [data-callout-title],
  [data-callout][data-callout-type="help"] > [data-callout-title],
  [data-callout][data-callout-type="faq"] > [data-callout-title] {
    color: rgb(249, 115, 22);
  }
  
  [data-callout][data-callout-type="question"] > [data-callout-title]::before,
  [data-callout][data-callout-type="help"] > [data-callout-title]::before,
  [data-callout][data-callout-type="faq"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxnIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiI+PGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iMTAiLz48cGF0aCBkPSJNOS4wOSA5YTMgMyAwIDAgMSA1LjgzIDFjMCAyLTMgMy0zIDNtLjA4IDRoLjAxIi8+PC9nPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="question"] > [data-callout-title]:empty::after {
    content: "Question";
  }
  
  [data-callout][data-callout-type="help"] > [data-callout-title]:empty::after {
    content: "Help";
  }
  
  [data-callout][data-callout-type="faq"] > [data-callout-title]:empty::after {
    content: "FAQ";
  }
  
  [data-callout][data-callout-type="warning"],
  [data-callout][data-callout-type="caution"],
  [data-callout][data-callout-type="attention"] {
    border-color: rgba(234, 88, 12, 0.2);
    background-color: rgba(251, 146, 60, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="warning"],
  html.dark [data-callout][data-callout-type="caution"],
  html.dark [data-callout][data-callout-type="attention"] {
    border-color: rgba(194, 65, 12, 0.2);
    background-color: rgba(249, 115, 22, 0.1);
  }
  
  [data-callout][data-callout-type="warning"] > [data-callout-title],
  [data-callout][data-callout-type="caution"] > [data-callout-title],
  [data-callout][data-callout-type="attention"] > [data-callout-title] {
    color: rgb(249, 115, 22);
  }
  
  [data-callout][data-callout-type="warning"] > [data-callout-title]::before,
  [data-callout][data-callout-type="caution"] > [data-callout-title]::before,
  [data-callout][data-callout-type="attention"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0ibTIxLjczIDE4bC04LTE0YTIgMiAwIDAgMC0zLjQ4IDBsLTggMTRBMiAyIDAgMCAwIDQgMjFoMTZhMiAyIDAgMCAwIDEuNzMtM00xMiA5djRtMCA0aC4wMSIvPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="warning"] > [data-callout-title]:empty::after {
    content: "Warning";
  }
  
  [data-callout][data-callout-type="caution"] > [data-callout-title]:empty::after {
    content: "Caution";
  }
  
  [data-callout][data-callout-type="attention"] > [data-callout-title]:empty::after {
    content: "Attention";
  }
  
  [data-callout][data-callout-type="failure"],
  [data-callout][data-callout-type="fail"],
  [data-callout][data-callout-type="missing"] {
    border-color: rgba(220, 38, 38, 0.2);
    background-color: rgba(248, 113, 113, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="failure"],
  html.dark [data-callout][data-callout-type="fail"],
  html.dark [data-callout][data-callout-type="missing"] {
    border-color: rgba(185, 28, 28, 0.2);
    background-color: rgba(239, 68, 68, 0.1);
  }
  
  [data-callout][data-callout-type="failure"] > [data-callout-title],
  [data-callout][data-callout-type="fail"] > [data-callout-title],
  [data-callout][data-callout-type="missing"] > [data-callout-title] {
    color: rgb(239, 68, 68);
  }
  
  [data-callout][data-callout-type="failure"] > [data-callout-title]::before,
  [data-callout][data-callout-type="fail"] > [data-callout-title]::before,
  [data-callout][data-callout-type="missing"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTIwIDZMOSAxN2wtNS01Ii8+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="failure"] > [data-callout-title]:empty::after {
    content: "Failure";
  }
  
  [data-callout][data-callout-type="fail"] > [data-callout-title]:empty::after {
    content: "Fail";
  }
  
  [data-callout][data-callout-type="missing"] > [data-callout-title]:empty::after {
    content: "Missing";
  }
  
  [data-callout][data-callout-type="danger"],
  [data-callout][data-callout-type="error"] {
    border-color: rgba(220, 38, 38, 0.2);
    background-color: rgba(248, 113, 113, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="danger"],
  html.dark [data-callout][data-callout-type="error"] {
    border-color: rgba(185, 28, 28, 0.2);
    background-color: rgba(239, 68, 68, 0.1);
  }
  
  [data-callout][data-callout-type="danger"] > [data-callout-title],
  [data-callout][data-callout-type="error"] > [data-callout-title] {
    color: rgb(239, 68, 68);
  }
  
  [data-callout][data-callout-type="danger"] > [data-callout-title]::before,
  [data-callout][data-callout-type="error"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLXphcCI+PHBhdGggZD0iTTQgMTRhMSAxIDAgMCAxLS43OC0xLjYzbDkuOS0xMC4yYS41LjUgMCAwIDEgLjg2LjQ2bC0xLjkyIDYuMDJBMSAxIDAgMCAwIDEzIDEwaDdhMSAxIDAgMCAxIC43OCAxLjYzbC05LjkgMTAuMmEuNS41IDAgMCAxLS44Ni0uNDZsMS45Mi02LjAyQTEgMSAwIDAgMCAxMSAxNHoiLz4+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="danger"] > [data-callout-title]:empty::after {
    content: "Danger";
  }
  
  [data-callout][data-callout-type="error"] > [data-callout-title]:empty::after {
    content: "Error";
  }
  
  [data-callout][data-callout-type="bug"] {
    border-color: rgba(220, 38, 38, 0.2);
    background-color: rgba(248, 113, 113, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="bug"] {
    border-color: rgba(185, 28, 28, 0.2);
    background-color: rgba(239, 68, 68, 0.1);
  }
  
  [data-callout][data-callout-type="bug"] > [data-callout-title] {
    color: rgb(239, 68, 68);
  }
  
  [data-callout][data-callout-type="bug"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxnIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiI+PHBhdGggZD0ibTggMmwxLjg4IDEuODhtNC4yNCAwTDE2IDJNOSA3LjEzdi0xYTMuMDAzIDMuMDAzIDAgMSAxIDYgMHYxIi8+PHBhdGggZD0iTTEyIDIwYy0zLjMgMC02LTIuNy02LTZ2LTNhNCA0IDAgMCAxIDQtNGg0YTQgNCAwIDAgMSA0IDR2M2MwIDMuMy0yLjcgNi02IDZtMCAwdi05Ii8+PHBhdGggZD0iTTYuNTMgOUM0LjYgOC44IDMgNy4xIDMgNW0zIDhIMm0xIDhjMC0yLjEgMS43LTMuOSAzLjgtNE0yMC45NyA1YzAgMi4xLTEuNiAzLjgtMy41IDRNMjIgMTNoLTRtLS44IDRjMi4xLjEgMy44IDEuOSAzLjggNCIvPjwvZz48L3N2Zz4=");
  }
  
  [data-callout][data-callout-type="bug"] > [data-callout-title]:empty::after {
    content: "Bug";
  }
  
  [data-callout][data-callout-type="example"] {
    border-color: rgba(126, 34, 206, 0.2);
    background-color: rgba(192, 132, 252, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="example"] {
    border-color: rgba(109, 40, 217, 0.2);
    background-color: rgba(168, 85, 247, 0.1);
  }
  
  [data-callout][data-callout-type="example"] > [data-callout-title] {
    color: rgb(168, 85, 247);
  }
  
  [data-callout][data-callout-type="example"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTggNmgxM004IDEyaDEzTTggMThoMTNNMyA2aC4wMU0zIDEyaC4wMU0zIDE4aC4wMSIvPjwvc3ZnPg==");
  }
  
  [data-callout][data-callout-type="example"] > [data-callout-title]:empty::after {
    content: "Example";
  }
  
  [data-callout][data-callout-type="quote"],
  [data-callout][data-callout-type="cite"] {
    border-color: rgba(82, 82, 91, 0.2);
    background-color: rgba(161, 161, 170, 0.2);
  }
  
  html.dark [data-callout][data-callout-type="quote"],
  html.dark [data-callout][data-callout-type="cite"] {
    border-color: rgba(63, 63, 70, 0.2);
    background-color: rgba(82, 82, 91, 0.15);
  }
  
  [data-callout][data-callout-type="quote"] > [data-callout-title],
  [data-callout][data-callout-type="cite"] > [data-callout-title] {
    color: rgb(82, 82, 91);
  }
  
  [data-callout][data-callout-type="quote"] > [data-callout-title]::before,
  [data-callout][data-callout-type="cite"] > [data-callout-title]::before {
    mask-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxZW0iIGhlaWdodD0iMWVtIiB2aWV3Qm94PSIwIDAgMjQgMjQiPjxwYXRoIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTMgMjFjMyAwIDctMSA3LThWNWMwLTEuMjUtLjc1Ni0yLjAxNy0yLTJINGMtMS4yNSAwLTIgLjc1LTIgMS45NzJWMTFjMCAxLjI1Ljc1IDIgMiAyYzEgMCAxIDAgMSAxdjFjMCAxLTEgMi0yIDJzLTEgLjAwOC0xIDEuMDMxVjIwYzAgMSAwIDEgMSAxbTEyIDBjMyAwIDctMSA3LThWNWMwLTEuMjUtLjc1Ny0yLjAxNy0yLTJoLTRjLTEuMjUgMC0yIC43NS0yIDEuOTcyVjExYzAgMS4yNS43NSAyIDIgMmguNzVjMCAyLjI1LjI1IDQtMi43NSA0djNjMCAxIDAgMSAxIDEiLz4+PC9zdmc+");
  }
  
  [data-callout][data-callout-type="quote"] > [data-callout-title]:empty::after {
    content: "Quote";
  }
  
  [data-callout][data-callout-type="cite"] > [data-callout-title]:empty::after {
    content: "Cite";
  }
</style>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    document.querySelectorAll('blockquote').forEach(blockquote => {
      const children = Array.from(blockquote.children);
      const firstChild = children[0];
  
      if (!firstChild || firstChild.tagName !== 'P') return;
  
      const firstLine = firstChild.innerHTML.split(/<br\s*\/?>|\n/)[0];
      const match = firstLine.match(/^\[!(.*?)\]\s?(.*)?/);
  
      if (!match) return;
  
      const type = match[1]?.trim().toLowerCase() || 'note';
      let title = match[2]?.trim().replace(/<[^>]*>/g, "") || (type.charAt(0).toUpperCase() + type.slice(1));
  
      // Remove the first paragraph's callout tag from the body
      firstChild.innerHTML = firstChild.innerHTML.replace(/^\[!(.*?)\]\s?/, '');
  
      // Collect the remaining HTML as the body
      const bodyHtml = children.map(child => child.outerHTML).join('');
  
      const newHtml = `
        <div data-callout data-callout-type="${type}">
          <div data-callout-title>${title}</div>
          <div data-callout-body>${bodyHtml}</div>
        </div>
      `;
      
      blockquote.outerHTML = newHtml;
    });
  });
</script>
```
