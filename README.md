# Danbooru Prompt Builder

Official version: https://tags.novelai.dev

Beta: https://tags-dev.novelai.dev

## Development and Improvement

### Edit tags or presets

please edit `data/tags/*.yaml` and `data/presets/*.yaml` file.

#### Expand

The minimum standard for adding tags is to have the English and Chinese names of the tags.

For label names, replace underscores with spaces. Be careful not to repeat with other tags. Use `npm run dupcheck` or `yarn dupcheck` to check for duplicates.

#### Refine

A good tag should have an image, description, alias and a link to the Danbooru Wiki.

The image size should be as close as possible to 512px * 512px for the best display effect.
Please add images to the public directory via `npm run importimage <path>` or `yarn importimage <path>`.
This will automatically crop the image and compress it appropriately.

Please do not add images to the project that are related to child pornography, or that violate the GitHub Terms of Use.

### Upload Refinement Model (TI Embeddings)

The refined model only supports the latest image format（`Save images with embedding in PNG chunks`）。
For security reasons, `.pt` model files are not accepted.

`.pt` The model file in the format is available through [this Colab Notebook](https://colab.research.google.com/gist/wfjsw/2b2a26349bef1ce891f6ab4d4fb3030a/convert-pt-embedding-to-png.ipynb) and do format conversion。

Add model images to the public directory. Then, create description files in `data/embeddings/**/*.yaml`.

```yaml
# The command used to call the model (the content of the angle brackets in the upper left corner of the model image)
prompt: victorian-lace
# Model name
name: Victorian Lace
# Model author
author: Reddit user u/depfakacc
# Model description
description: "A lace pattern that looks like it was made in the Victorian era."
# Model classification
category: uncategorized
# The name of the main model corresponding to this model
modelName: model-aa-waifu
# The main model Hash corresponding to this model (the Hash displayed in the WebUI drop-down box)
modelHash: 2037c511
# The number next to the v character in the lower right corner of the model image
vectorSize: 10
# The number next to the s character in the lower right corner of the model image
steps: 675
# Model filename, without suffix
filename: victorian-lace
# Model file SHA256 Hash
payloadHash: df0641662fb2fc8190a4508c34926243843484495e6d9b0e500f8a8e409aa84e
```

### Development Environment

> Due to the use of some Pro icons, building this project will require [Font Awesome v6 Pro Authorize](https://fontawesome.com/plans)，
> And connect to the Font Awesome private NPM server. You can temporarily replace with the Free icon during development.

```bash
# Install dependencies
yarn
# Start the development server
yarn dev 
# Build the project
yarn build 
```
