# Plaintext Blog Themer

An opinionated themer for configuring and visualizing what your plaintext blog will look like.

You can see your poor choices in full glory for the following:

1. Headings: Font, Color
2. Text: Font, Color
3. Background Color

I made this to see what my (Bear) blog would look like without having to rebuild and deploy it. I am lazy.

But most importantly, this app is an excuse for me to see what [Svelte](https://svelte.dev/) is all about.
So far, I really like it.

## Development

Clone this repository, `cd` into it, and run `npm install` (or `pnpm install` or `yarn`) to install the dependencies.

Then, you can start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Build

To create a production version:

```bash
npm run build
```

Preview the production build with `npm run preview`.

## Credits

This project:

1. Will eventually look great because of [Bits UI](https://www.bits-ui.com/docs/introduction), or [Flowbite](https://flowbite-svelte.com/), if I'm feeling lazy.
2. Was bootstrapped with [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).
