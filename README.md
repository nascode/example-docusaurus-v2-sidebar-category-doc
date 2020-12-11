## Docusaurus v2: Show Document On Sidebar Category Click

_My Docusaurus v2 is on 2.0.0-alpha.69 when creating this example repo_

Some users of Docusaurus v2 want to make sidebar category clickable and show relevant doc (maybe some intro or TOC). Unfortunately it's not supported yet. See [this issue](https://github.com/facebook/docusaurus/issues/2643) and [this issue](https://github.com/facebook/docusaurus/issues/3686)

My aim is to customize Docusaurus v2 without changing it too much. Lets go step by step from starting new Docusaurus v2 project with classic theme:

### 1. Init New Project With Classic Theme

`npx @docusaurus/init@latest init docusaurus-playground classic`

### 2. Prepare Sidebar Data

in `sidebars.js`

```
module.exports = {
  someSidebar: {
    "Category One": ["toc1", 'doc1', 'doc2', 'doc3'],
    "Category Two": ["toc2", 'mdx'],
  },
};
```

We will use first index in each array as catagory doc.

### 3. Swizzle DocSidebar Component

Copy classic theme's component that we want to modify.

```
yarn run swizzle @docusaurus/theme-classic DocSidebar
```

Do not forget to restart dev server after swizzling.

### 4. Modify DocSidebar index.js

We will modify `DocSidebarItemLink` component. Look at the code in this repo.

### 5. Test it!