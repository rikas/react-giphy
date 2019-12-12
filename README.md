# react-giphy

We are going to build a simple app that integrates with [Giphy](https://giphy.com) to show a list of gifs, based on some search string.

![Giphy preview](https://cl.ly/c49dfd2d7338/giphy_small.png)

## Specs

Your app should have the following features:
  * Think about the component structure in the app. Try **immutable** first (model data with props).
  * The user should be able to click on one of the gifs on the right sidebar to make it appear in the left area
  * The list of gifs should change when the user types a search string

### Giphy API

You will need to get an api key from https://developers.giphy.com/ and to interact with the API there's a NPM package for that:

```bash
yarn add giphy-api
```

Documentation: https://www.npmjs.com/package/giphy-api

**Note**: as the user types your app will make API calls to search for gifs. Probably you will have problems because if you're not careful you'll actually do one API call everytime the user types a character. We can avoid this by having a **debounce** behaviour. Luckily there's a NPM package to solve the problem - `react-debounce-input`

## Boilerplate

Basic CSS styles to be used in the app: http://bit.ly/giphy-styles

Bootstrap 4: https://www.bootstrapcdn.com/ (add the CDN link to your <head> in index.html)

Fontawesome: https://www.bootstrapcdn.com/fontawesome/ (add the CDN link to your <head> in index.html)
