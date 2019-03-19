# Isogeo - Scan FME documentation

[![CircleCI](https://circleci.com/gh/isogeo/doc-scan-fme/tree/master.svg?style=svg&circle-token=c5ff09dcfc8035307bd4760b18d45c6e7bb3c85b)](https://circleci.com/gh/isogeo/doc-scan-fme/tree/master)

Content, structure and media of the website documentation. It's part of the Isogeo online documentations ([see Github repositories](https://github.com/search?q=topic%3Adocumentation+org%3Aisogeo&type=Repositories)).

## Edit this documentation

It's based on Gitbook v3.2.* which is:

* [a book format](https://github.com/GitbookIO/gitbook)
* [a toolchain](https://toolchain.gitbook.com/)

## Deployment

It's deployed on Isogeo Azure (Storage v2 Static website) using CircleCI ([see config](https://github.com/isogeo/doc-scan-fme/blob/master/.circleci/config.yml)):

* QA: <https://qaisogeohelp.z28.web.core.windows.net/scan/>
* PROD: <https://prodisogeohelp.z28.web.core.windows.net/scan/>

Deployment rules:

* each commit triggers a deployment on QA
* each tagged commit triggers a deployment on PROD - [see tags](https://github.com/isogeo/doc-scan-fme/tags)
