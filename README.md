# linaria vite ssr dev issue

This repo is a reproduction for the issue where Vite in dev mode does not inline the linaria CSS in the server rendered html.
The styles kicks in only after the react hydration and the vite runtime kicks in.

This results in a very bad flicker of the UI from a state of no styles to a state where styles are actually loaded.

This becomes a big issue as the project grows, since in big projects the number of files Vite has to request in dev is very high and resulting in a few seconds of styles not being loaded in the server rendered html.

## command

```sh
yarn dev
```

## Issues

- https://github.com/callstack/linaria/issues/1404
- https://github.com/Anber/wyw-in-js/issues/78
