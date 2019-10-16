# kus.lviv.ua

![kus](images/logo.svg)

Repo for a baking blog at https://kus.lviv.ua/

## Develop

1. Install Jekyll locally

    ```sh
    bundle install --path vendor/bundle
    ```

2. Run Jekyll

    ```sh
    bundle exec jekyll serve --watch --drafts
    ```

## Process images

- Re-align images using [`Hugin`](https://wiki.panotools.org/Align_image_stack)

    ```sh
    align_image_stack -a aligned -C *.jpg
    ```

- Create GIF from JPGs using `ImageMagick`

    ```sh
    convert -delay 10 -loop 0 *.jpg file.gif
    ```
