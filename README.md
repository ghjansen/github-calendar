<!-- Please do not edit this file. Edit the `blah` field in the `package.json` instead. If in doubt, open an issue. -->


















# github-calendar.js

 [![Version](https://img.shields.io/npm/v/github-calendar.svg)](https://www.npmjs.com/package/github-calendar) [![Downloads](https://img.shields.io/npm/dt/github-calendar.svg)](https://www.npmjs.com/package/github-calendar)







> Embed your GitHub contributions calendar anywhere.







Everybody<sup><sup>well, haters gonna hate</sup></sup> loves GitHub and everybody loves stats. So, why not making the GitHub contributions calendar available for being embeded in your web pages? Now [you can](https://bloggify.github.io/github-calendar/example). :tada:


[![](https://i.imgur.com/tJjRpuN.png)](https://bloggify.github.io/github-calendar/example)













## :cloud: Installation


Check out the [`dist`](/dist) directory to download the needed files and include them on your page.

If you're using this module in a CommonJS environment, you can install it using `npm` or `yarn` and `require` it:

```sh
# Using npm
npm install --save github-calendar

# Using yarn
yarn add github-calendar
```

















```html
<!-- Include the library. -->
<script
  src="https://unpkg.com/github-calendar@latest/dist/github-calendar.min.js">
</script>

<!-- Optionally, include the theme (if you don't want to struggle to write the CSS) -->
<link
  rel="stylesheet"
  href="https://unpkg.com/github-calendar@latest/dist/github-calendar-responsive.css"
/>

<!-- Prepare a container for your calendar. -->
<div class="calendar">
    <!-- Loading stuff -->
    Loading the data just for you.
</div>

<script>
    GitHubCalendar(".calendar", "your-username");

    // or enable responsive functionality:
    GitHubCalendar(".calendar", "your-username", { responsive: true });

    // Use a proxy
    GitHubCalendar(".calendar", "your-username", {
       proxy (username) {
         return fetch(`https://your-proxy.com/github?user=${username}`)
       }
    }).then(r => r.text())
</script>
```


[Here](https://bloggify.github.io/github-calendar/example/) you can see this example in action.







## :question: Get Help

There are few ways to get help:



 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:





## :memo: Documentation


### `GitHubCalendar(container, username, options)`
Brings the contributions calendar from GitHub (provided username) into your page.

#### Params

- **String|HTMLElement** `container`: The calendar container (query selector or the element itself).
- **String** `username`: The GitHub username.
- **Object** `options`: An object containing the following fields:
   - `summary_text` (String): The text that appears under the calendar (defaults to: `"Summary of
     pull requests, issues opened, and commits made by <username>"`).
   - `proxy` (Function): A function that receives as argument the username (string) and should return a promise resolving the HTML content of the contributions page.
     The default is using @Bloggify's APIs.
   - `global_stats` (Boolean): If `false`, the global stats (total, longest and current streaks) will not be calculated and displayed. By default this is enabled.
   - `responsive` (Boolean): If `true`, the graph is changed to scale with the container. Custom CSS should be applied to the element to scale it appropriately. By default this is disabled.
   - `tooltips` (Boolean): If `true`, tooltips will be shown when hovered over calendar days. By default this is disabled.
   - `cache` (Number) The cache time in seconds.

#### Return
- **Promise** A promise returned by the `fetch()` call.














## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].
















## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - `@pengliheng/github-report`
 - `@axetroy/react-github-calendar`
 - `github-alike-calendar`
 - `@philipwhiuk/react-github-calendar`
 - `react-ts-github-calendar`











## :scroll: License

[MIT][license] © [Bloggify][website]






[license]: /LICENSE
[website]: https://bloggify.org
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
