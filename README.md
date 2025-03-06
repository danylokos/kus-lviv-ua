# kus.lviv.ua

![kus](images/logo.svg)

Repo for a baking blog at https://kus.lviv.ua/

## Develop

1. Configure dependecies (once)

    ```sh
    docker run --rm -it \
        -v "$(pwd):/srv/jekyll" \
        -v "$(pwd)/vendor/bundle:/usr/local/bundle" \
        -p 4000:4000 \
        jekyll/jekyll \
        bundle config set --local path /usr/local/bundle
    ```

2. Run Jekyll

    ```sh
    docker run --rm -it \
        -v "$(pwd):/srv/jekyll" \
        -v "$(pwd)/vendor/bundle:/usr/local/bundle" \
        -p 4000:4000 \
        jekyll/jekyll \
        jekyll serve --watch --drafts
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
