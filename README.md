# shopify-theme

### Step 1

Create new theme using Shopify ThemeKit [Read more](https://shopify.dev/docs/themes/tools/theme-kit/command-reference#new).

<details>

<summary>Get theme password</summary>

#### Install - [Theme Access app](https://apps.shopify.com/theme-access?shpxid=57843a18-19C5-4058-9557-39DC6B42171E)

</details>

```bash
$ theme new --password=[your-theme-kit-password] --store="[your-store.myshopify.com]" --name="Your Theme Name"
```

### Step 2

Install Tailwindcss with Postcss - [documentation](https://tailwindcss.com/docs/installation/using-postcss).

<details>

<summary>Guide</summary>

Install Tailwindcss

```bash
# you can use other package manager (e.g npm, yarn)
$ pnpm install -D tailwindcss postcss autoprefixer
```

Generate tailwind.config.js and postcss.config.js

```bash
$ npx tailwindcss init -p
```

tailwind.config.js

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
	content: ["./**/*.liquid", "./src/**/*.{js,ts,jsx,tsx}"],
	theme: {
		extend: {},
	},
	plugins: [],
};
```

src/theme.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

package.json

```json
{
	"scripts": {
		"postcss": "postcss ./src/theme.css -o ./assets/theme.css.liquid"
	}
}
```

Run and generate tailwindcss assets/theme.css.liquid

```bash
# you can use other package manager (e.g npm, yarn)
$ pnpm run postcss
```

</details>
