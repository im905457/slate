---
title: Kono smarticle API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - response

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - magazines
  - issues
  - articles
  - images
  - videos
  - audios
  - errors

search: true
---

# Introduction

Welcome to the kono smarticle API! You can use our API to access API endpoints, which can get content of magazines, articles, and various article assets in kono smarticle reading service.

### HOST

env | host
--- | -----------
prod | TBD
dev  | https://smarticle-api.sandbox.thekono.com

# Authentication

Kono smarticle expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-Smarticle-Id: smarticle_api_key`

You must replace <code>smarticle_api_key</code> with your API key.
