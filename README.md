# respec-oas

**respec-oas** is a ReSpec plugin that integrates OpenAPI Specification (OAS)
data directly into ReSpec specifications. It enables dynamic rendering of API
summaries, endpoint details, request/response schemas, and expected caller
information using OpenAPI YAML files.

## Features

- ✅ Validates multiple OpenAPI YAML documents
- 📄 Renders:
  - API summary tables
  - Endpoint-level details
  - JSON Schema request/response formats

## Installation

To include `respec-oas` in your ReSpec-based document, add the following
to your HTML:

```html
<script class="remove"
  src="https://cdn.jsdelivr.net/gh/digitalbazaar/respec-oas@0.8.0/dist/main.js">
</script>
```

## Usage

### 1. Define Tables and Sections in Your HTML

Add these classes to `<table>` or `<section>` elements:

```html
<table class="api-summary-table" data-api-path="/example-path /another-path"></table>
<table class="api-component-table" data-api-path="/example-path"></table>
<section class="api-detail" data-api-endpoint="post /example-path"></section>
```

### 2. Load `respec-oas`

Ensure your document or script environment has access to `respec-oas`. For example:

```html
<script class="remove"
  src="https://cdn.jsdelivr.net/gh/digitalbazaar/respec-oas@0.8.0/dist/main.js">
</script>
```

and then call it from the respec configuration in a post-processing step:

```js
    postProcess: [window.respecOas.injectOas],
```

## Release Process

To make a new release:

```code
Checkout main (merge any PRs to main).
checkout -b v1.0.x for a new release.
nvm use 24
Update release to 1.0.x in package.json 
npm build
git add dist/* 
git commit -a
git tag 1.0.x
git push --tags
```
