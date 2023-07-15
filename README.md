# MiniGPT4-image-labeler
This repository is for running [MiniGPT-4](https://minigpt-4.github.io/) on Google Colab as a way to label your images for fine tuning Stable Diffusion models

The system is split into two parts: a server and a client. The server will be serving MiniGPT-4 using [oobabooga's text generation ui](https://github.com/oobabooga/text-generation-webui) through its API functionality. Since it'll be hosted on Google Colab, it'll use Cloudflare to open a tunnel that'll allow other computers to access it.

The client will take a folder of image files and send unlabeled ones to the server to be labeled. Although you don't need this client to use MiniGPT-4 per se, without it, you'll be manually querying every image individually and copying and pasting the resulting labels into text files. The client provides a way of automatically labeling your images without taking up much of your time and attention.

## Running the Server

Open either the [server_latest.ipynb](https://github.com/xjdeng/MiniGPT4-image-labeler/blob/main/server_latest.ipynb) or [server_failsafe.ipynb](https://github.com/xjdeng/MiniGPT4-image-labeler/blob/main/server_failsafe.ipynb) notebook on Google Colab (there should be a link when you open either file.) The latest one might not work if future updates to its dependencies break it but the failsafe version should, albeit an older version especially when you're reading this. If you're not willing to troubleshoot and debug, I'd stick with the failsafe version.

The follow along with the instructions, making sure you copy the URL to the non-streaming (not streaming) server which you'll need to input later into the client notebook. Make sure the links to the Gradio interfaces have also appeared before you start running the client (you don't need to use the Gradio interface but they won't appear until the server has completely started up.

Occasionally, errors might prevent either the streaming or non-streaming server from starting but as long as the non-streaming server has started, you should be able to copy the URL and paste it in the respective box in the client notebook.  If the non-streaming server has failed to start, you may need to restart the last cell (there's no need to restart the entire notebook.)

## Running the Client

