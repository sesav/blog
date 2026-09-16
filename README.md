# 8am.dev Blog

The source code for this [blog](https://8am.dev).

## How to start

[Install Zola](https://www.getzola.org/documentation/getting-started/installation/) and run a
single command. Zola will automatically rebuild and reload the site as you make changes.

All you need to do is edit the `config.toml` file, and you're ready to start writing posts.

Clone the repo:
```shell
$ git clone https://github.com/sesav/blog.git
```

Go to the `blog/` folder, edit the `config.toml` according to your needs:
```shell
$ cd blog/
$ nvim config.toml
```

When everything is ready, run Zola to start the blog:
```shell
$ zola serve
```

## Requirements

There are no requirements or additional dependencies.

The [style guide](https://8am.dev/page/styleguide) renders every markdown construct
this blog supports, on one page, for eyeballing typography.
