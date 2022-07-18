---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
---

# CI/CD

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: center
background: https://source.unsplash.com/collection/94734566/1920x1080
---

<Toc />

---

<div class="flex flex-col h-full">
<h1>什么是 CI/CD?</h1>

<section>
<div class="icon" v-click>
  <flat-color-icons-idea class="text-3xl" />idea
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<material-symbols-featured-play-list-outline class="text-3xl" />feature
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<carbon-code class="text-3xl" />implement
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<file-icons-test-js class="text-3xl" />test
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<akar-icons-shipping-box-01 class="text-3xl" />build
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<clarity-deploy-line class="text-3xl inline-block slidev-icon" />deploy
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<emojione-eye-in-speech-bubble class="text-3xl" />observe
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
<material-symbols-bug-report class="text-3xl" />bug
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon" v-click>
  <flat-color-icons-idea class="text-3xl" />idea
</div>
</section>

<p v-click>这就是正常我们开发的流程, 可以看到这是永不停歇的, 形成了一个环</p>

<div grid="~ cols-2 gap-4 mt-2" style="flex: 1">
<div v-click class="flex flex-col">

<h2 class="text-center">CI</h2>

<section class="flex items-center justify-center flex-1">
<div class="icon">
  <file-icons-test-js class="text-3xl" />test
</div>
<carbon-arrow-right class="text-3xl" v-click/>
<div class="icon">
  <akar-icons-shipping-box-01 class="text-3xl" />build
</div>
</section>

</div>
<div v-click class="flex flex-col">

<h2 class="text-center">CD</h2>

<section class="flex items-center justify-center flex-1">
<div class="icon">
  <clarity-deploy-line class="text-3xl inline-block slidev-icon" />deploy
</div>
</section>

</div>
</div>
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
section {
  display: flex;
  align-items: center;
  column-gap: 8px;
}
.icon {
  display: inline-flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

---

# 持续集成 continuous integration

<div>当开发人员代码 commit 到 git 仓库的时候会触发 pipeline, 我们有迭代分支, 每个开发人员并行的开发自己相应的功能, 那就很有可能在合并代码的时候产生冲突, 当开发人员开发的周期越长, 那么产生的冲突很可能就会更多, 你不知道你会影响到哪些功能, 所以我们就会有自动化测试来测试我们的代码, 改的越多, 自动化测试下来可能就有很多报错, 我们就需要修改, 让所有测试都✅</div>

<h2 class="text-center mb-4">优势</h2>

- 🧑‍💻 **提升开发效率** - 持续集成可将开发人员从手动任务中解放出来，并且鼓励有助于减少发布到客户环境中的错误和缺陷数量的行为，从而提高团队的工作效率。
- 🐞 **更快发现并解决缺陷** - 通过更频繁的测试，您的团队可以在缺陷稍后变成大问题前发现并解决这些缺陷。
- ✅ **更快交付更新** - 持续集成有助于您的团队更快、更频繁地向客户交付更新。
- 😄 **双赢** - 生产环境更少的 bug，意味着用户更好的使用体验，对于公司则给用户留下了更好的声誉

<style>
  h1 {
    background-color: #2B90B6;
    background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
    background-size: 100%;
    -webkit-background-clip: text;
    -moz-background-clip: text;
    -webkit-text-fill-color: transparent;
    -moz-text-fill-color: transparent;
  }
</style>
---

# CD 的全称是什么?
## 持续交付 continuous delivery/持续部署 continuous deployment

一般来说是指持续交付, 而不是持续部署, 两者之间有什么不同? 在持续交付的 CI/CD pipeline 里, “自动化” 是有一个度的, 在我们的制品要推上生产的时候, 就没有自动化了, 需要我们手动的去推送制品. 

而自动的将我们的制品推送到生产, 这一个步骤就是持续部署

一般我们会分阶段部署, 方便我们在真正推到生产上的时候做一些测试以及修改

<img src="https://d1.awsstatic.com/product-marketing/DevOps/continuous_delivery.4f4cddb8556e2b1a0ca0872ace4d5fe2f68bbc58.png"/>

<style>
  h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# CI/CD 工具

<div grid="~ cols-2 gap-4">
<img v-click src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/image1-1.png"/>
<img v-click src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/image5.png"/>
<img v-click src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/image15.png"/>
<img v-click src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/github-actions-1.png"/>
</div>

---

# Jenkins VS GitLab

<div grid="~ cols-2 gap-4">
<section v-click>
<img src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/image1-1.png" style="height: 100px; margin: auto; margin-bottom: 2rem"/>
<ul>
优点
<li>功能强大, 开源, 拥有庞大的社区</li>
<li>非常灵活, 有很多现有的插件可以使用</li>
<li>19.2K Star & 7.5K Fork</li>
<li>可以集成到目前很多主流的云平台厂商, 例如: AWS, Google Cloud, Azure...</li>
</ul>
<ul class="mt-2">
缺点
<li>自身没有提供 SaaS</li>
</ul>
</section>
<section v-clicksli>
<img src="https://www.lambdatest.com/blog/wp-content/uploads/2020/10/image15.png" style="height: 100px; margin: auto; margin-bottom: 2rem"/>
<ul>
优点
<li>有很多开箱即用的功能, Self-Monitoring, Container Registry, Docker CI Runner</li>
<li>提供 CI/CD 功能的同时, 可以托管我们的代码</li>
<li>SaaS</li>
<li>有可视化界面</li>
</ul>
<ul class="mt-2">
缺点
<li>过于集成, 只能搭配 GitLab</li>
</ul>
</section>
</div>

<style>
  h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>
---

# Why GitHub Actions

- 🆓 **免费!!!** - 公共仓库和自托管运行器免费使用 GitHub Actions, 但是私有仓库则为 2000 分钟/月
- 💻 **多种虚拟机任君挑选** - Linux, Windows 和 macOS
- 🔠 **多种模版** - 有许多其他开发者写好的模版可以直接使用

---

# GitHub Actions

You can configure a GitHub Actions *workflow* to be triggered when an *event* occurs in your repository, such as a pull request being opened or an issue being created.
Your workflow contains one or more *jobs* which can run in sequential order or in parallel.
Each job will run inside its own virtual machine *runner*, or inside a container, and has one or more steps that either run a script that you define or run an *action*, which is a reusable extension that can simplify your workflow.

<img src="https://docs.github.com/assets/cb-25535/images/help/images/overview-actions-simple.png"/>

---

Workflow 是一个可配置的自动化流程, 可以跑一个或者多个 job,
是一个 YAML 文件, 对应的 event 触发就会运行. 一般放在固定的位置, <code>.github/workflows</code>

```yaml {all|1|2|3|4|5|6|7|8-10|11|12|all}
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

<style>
  h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: center
---

<h1 class="text-center">Demo</h1>

<a href="vscode://Users/baba/Documents/workspace_baba/Blog">自动部署到 GitHub Page</a>