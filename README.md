[![ColorMagic banner](./.github/assets/banner.png)](https://colormagic.app)

# 🎨 [ColorMagic](https://colormagic.app)

ColorMagic is a free and open-source color palette generator, with many side-tools for all things color. It's built with [Nuxt](https://nuxt.com), [NuxtUI](https://ui.nuxt.com) and typescript.

Most of the tools run with the assitance of AI using [openai](https://openai.com).

The site has translations for [english](https://colormagic.app), [japanese](https://colormagic.app/ja) and [italian](https://colormagic.app/it) using [nuxtjs/i18n](https://i18n.nuxtjs.org/).

## <a name="structure">🏗️ Structure</a>

ColorMagic utilize Nuxt's in-built layers system to seperate domains of the app. 

Each layer creates it's own seperate module ([example](/layers/palette/server/palette.module.ts)) which we then declare in the [setup util](/layers/setup/server/utils/setup.util.ts). The modules are then available to use globally.

## <a name="database">📦 Database</a>

All of ColorMagic's palettes are stored in MongoDB. You can setup a local mongoDB instance by using the following:

```bash
docker compose up
```

For more details check out the [mongo layer](/layers/mongo/server/mongo.module.ts).

## <a name="getting-started">🚀 Getting Started</a>
Create a .env in the root of the project and add the following values:
```env
OPENAI_API_KEY=[sk_srf4s...]
```

Use the following command to start it up locally
```bash
npm install
npm run dev
```

## <a name="color-tools">🔧 Color Tools</a>

- 🎨 [Color Palette Generator](https://colormagic.app/)
- ❓ [Random Color generator](https://colormagic.app/random-color)
- 🖼️ [Image Color Picker](https://colormagic.app/image-color-picker)

This is a WIP, more tools coming soon!

## <a name="api">🖥️ API</a>

ColorMagic has a public API that anyone can use free of charge. 

We use the awesome [@tanstack/vue-query](https://github.com/TanStack/query) for all API calls and [@sinclair/typebox](https://github.com/sinclairzx81/typebox) to validate on the server.

You can find the available public API endpoints [here](https://colormagic.app/api).

Please note: This API may be removed or changed at anytime, without warning. Use at your own risk.

## <a name="contribute">❤️ Contribute</a>

Feel free to suggest fixes or help with new features!
