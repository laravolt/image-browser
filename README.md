> [!IMPORTANT]
> **This repository is archived.** Use [`laravoltdev/image`](https://hub.docker.com/r/laravoltdev/image) instead ([source](https://github.com/laravolt/image)):
>
> - **Browser tests in CI:** `laravoltdev/image:php8.5-ci` has PHP 8.5 with pcov, Composer, Node.js, Bun and Playwright Chromium. For Firefox or WebKit, run `npx playwright install --with-deps firefox webkit` in your job.
> - **Local development:** `laravoltdev/image:php8.5-dev`.
>
> The `laravoltdev/image-browser` tags on Docker Hub stay available but get no updates. They stop at PHP 8.4 on a ServerSideUp beta base.

[![Release](https://img.shields.io/github/v/release/laravolt/image-browser)](https://github.com/laravolt/image-browser/releases)

## Introduction

Docker image for easier deployment of high-performance Laravolt applications with FrankenPHP base image from [ServerSideUp](https://serversideup.net).

## Compiled Image

Check the compiled image on Docker Hub: [https://hub.docker.com/r/laravoltdev/image-browser](https://hub.docker.com/r/laravoltdev/image-browser)
