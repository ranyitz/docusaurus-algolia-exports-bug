**TL;DR - This is a weird bug when the word exports in an h1-h5 tag causes the search to not work**

To recreate the bug:

1. Run `cd website`
2. Run `yarn`
3. Run `yarn start`
4. Navigate to `http://localhost:3000/docs/doc4`
5. Type something in the search bar

When looking at the devtools console/network tab, you can see that there aren't search (autocomplete) requests to algolia.

6. navigate to `http://localhost:3000/docs/doc5`
7. Type something in the search bar

Search request are sent as expected.

It seems that when using a header with the word `exports` the search stop working. Change [this line](https://github.com/ranyitz/docusaurus-algolia-exports-bug/blob/master/docs/exampledoc4.md#exports) and everything should work

Note: There are not valid algolia credentials, but you can see that the request doens't go out.
