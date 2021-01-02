This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
yarn dev
```

Open [http://localhost:8080](http://localhost:8080) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/import?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## 开发注意事项

1. 静态文件统一放入`public`文件夹下，注意：`public/svg`文件夹是有 loader 进行特殊处理的，只有需要使用`SvgIcon`组件的 svg 图片放到`public/svg`文件夹中，其余直接通过 src 引入的图片不要放到`public/svg`文件夹中。
   1. 图片的引入方式：HTML 文件中 src 属性使用`require('public/**/*.svg')`的格式引入，scss 文件中如果需要使用`background-image`属性，需要使用相对路径引入。
2. 公用组件放在`components`文件夹中，页面需要的组件在`modules`文件夹中新建页面文件夹，放到对应的页面文件夹中
3. 样式开发时，尽可能用`variables`中已有的变量，并且尽可能避免使用`id`选择器

## Release

1. Run `npm run release` to release new version, this command will does the following:

   - Checkout to `develop` and identifies current version and latest tag.
   - Prompts for a new version to select.
   - Create a release branch as `release-v1.0.0`
   - Modifies package metadata (package.json, package-lock.json, src/app/version.ts) to reflect new release and generate changelog
   - Commits those changes to release branch.
   - Pushes to the git remote.

   You can run `npm run release -- [patch|minor|major|2.0.0]` to skip the version selection prompt and increment the version by that keyword or specify version.

1. Submit pull request from release branch to master
1. Code review & merge pull request for release
1. Run `npm run pub` to create tag, this command will does the following:

   - Fetch latest code and checkout to `develop`
   - Create tag for new version
   - Pushes tags to git remote

   or you can create release tag go to github.

`npm run release -- --dry-run` or `npm run pub -- --dry-run`

running with the flag `--dry-run` allows you to see what commands would be run, without committing to git or updating files. (意思就是打印一下日志让你看看做了哪些步骤，但是并不会真的执行脚本，你可以放心的执行)
