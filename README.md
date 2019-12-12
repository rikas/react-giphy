# react-giphy

We are going to build a simple app that integrates with [Giphy](https://giphy.com) to show a list of gifs, based on some search string.

![Giphy preview](https://cl.ly/c49dfd2d7338/giphy_small.png)

## Specs

Your app should have the following features:
  * Think about the component structure in the app. Try **immutable** first (model data with props).
  * The user should be able to click on one of the gifs on the right sidebar to make it appear in the left area
  * The list of gifs should change when the user types a search string

### Showing gifs

In Giphy every gif has a source in the following format:

```
https://media.giphy.com/media/ID_OF_THE_GIF/giphy.gif
```

And this address can actually be copied for every image and they call it _GIF link_ (search for the link icon — the chain icon).

You can use the above URL to **dynamically** change the ID, depending on what you want to show!

### Giphy API

You will need to get an api key from https://developers.giphy.com/ and to interact with the API there's a NPM package for that:

```bash
yarn add giphy-api
```

Documentation: https://www.npmjs.com/package/giphy-api

#### Storing the API key

You can store your API key in a `.env` file, for example:

```
GIPHY_API='KI9wl2DyhOo51x2tscVMTti9cT1HeaeB'
```

And then read it in your JavaScript code by using `process.env.GIPHY_API`. Keep in mind that this still exposes your API key to the world as it will be present in the compiled version of your JavaScript.

#### Debouncing the inpute to avoid too many requests

As the user types your app will make API calls to search for gifs. Probably you will have problems because if you're not careful you'll actually do one API call everytime the user types a character. We can avoid this by having a **debounce** behaviour.

Luckily there's a NPM package to solve the problem - `react-debounce-input`

Documentation: https://www.npmjs.com/package/react-debounce-input

Example:

```jsx
<DebounceInput
   type="text"
   minLength={2}
   debounceTimeout={300}
   onChange={handleUpdate} />
```

## Boilerplate

Basic CSS styles to be used in the app: http://bit.ly/giphy-styles
