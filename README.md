# MiniGPT4-image-labeler
This repository is for running [MiniGPT-4](https://minigpt-4.github.io/) on Google Colab as a way to label your images for fine tuning Stable Diffusion models

The system is split into two parts: a server and a client. The server will be serving MiniGPT-4 using [oobabooga's text generation ui](https://github.com/oobabooga/text-generation-webui) through its API functionality. Since it'll be hosted on Google Colab, it'll use Cloudflare to open a tunnel that'll allow other computers to access it.

The client will take a folder of image files and send unlabeled ones to the server to be labeled. Although you don't need this client to use MiniGPT-4 per se, without it, you'll be manually querying every image individually and copying and pasting the resulting labels into text files. The client provides a way of automatically labeling your images without taking up much of your time and attention.
