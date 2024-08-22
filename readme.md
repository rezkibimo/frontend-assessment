Introduction
---
For this assessment, I use Nuxt 3 (Vue 3) and Tailwind CSS. Instructions to run the page locally are provided, and a live preview is available through Vercel.

## Setup
Go to the frontend-assessment-answer folder 

```cd frontend-assessment-answer```

Then make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev

# bun
bun run dev
```

Exercise 1
---
Build a responsive page based on the designs.

##### Requirements
1. Match the designs exactly. ✅
2. Needs to be responsive. ✅

For this exercise, I use the help of Figma to measure and approximate all the necessary sizing from padding, margin, gap and typography. 

https://www.figma.com/design/gUPaCo6i2Wy78LjECLM9en/Frontend-Assesment?node-id=0-1

To view the page when running the local server, navigate to the following URL: `http://localhost:3000`

Alternatively, use the link below to see a live preview:
https://frontend-assessment-wheat.vercel.app/

Exercise 2
---
Read the `data.json` file and display the data as tabs on desktop and an accordion on mobile.

##### Requirements
1. Display data in tabs on desktop. ✅
2. Display data in an accordion on mobile. ✅
3. Only 1 accordion/tab should be open at a time. ✅
4. Open the first accordion/tab on load. ✅
5. If the open accordion is selected, close it. ✅

###### Bonus points
* Improve the user experience with meaningful animations/transitions. ✅
* Design and styling. ✅
* Explain why the result of `('b' + 'a' + + 'a' + 'a').toLowerCase()` is `banana`. ✅

For this exercise, I utilized Nuxt (Vue) native dynamic component feature to change components based on conditions. Originally, the Accordion and Tab Group were the same component with different styling for various breakpoints. However, this approach became unorganized and difficult to maintain due to intertwined code. Therefore, I opted for the dynamic component approach. While this might impact performance slightly, it results in cleaner and more maintainable code overall.

To view the page when running the local server, navigate to the following URL: `http://localhost:3000/exercise-2`

Alternatively, use the link below to see a live preview:
https://frontend-assessment-wheat.vercel.app/exercise-2