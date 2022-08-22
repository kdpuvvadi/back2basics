# Back2Basics

Learn Basics with Back2Basics

## Setup

Clone the repo 

```bash
git clone https://github.com/kdpuvvadi/back2basics.git`
cd back2basics
```

Install Ruby and other prerequisites on `Ubuntu`

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```

Install Ruby and other prerequisites on `Fedora`

```bash
sudo dnf install ruby ruby-devel openssl-devel redhat-rpm-config @development-tools
```

Install Ruby and other prerequisites on `RHEL/RockyLinux`

```bash
sudo dnf install ruby ruby-devel
sudo dnf group install "Development Tools"
```

add env varibles to `~/.bashrc`

```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

install Jekyll and Bundler

```bash
gem install jekyll bundler
```

## Installing Dependencies

Install dependencies by running `bundle`

```bash
bundle
```

## Testing Locally

To run locally start a dev server with 

```bash
bundle exec jekyll s
```

Visit site at http://localhost:4000.

## Deploy on GitHub pages

* Build action is done with GitHub actions with `.github/workflows/pages-deploy.yml`. Please make sure branch is same as your working branch incase if you've changed the branch name.

* If you are running on `ARM64` environment likes of `apple's M1/M2` run

  ```bash
  bundle lock --add-platform x86_64-linux
  ```

* Push commits to GitHub and after build has completed, `gh-pages` branch will be created.

* Select the tab `Settings`, then click `Pages` in the left navigation bar, and then in the section Source of `GitHub Pages`, select the `/(root)` directory of branch `gh-pages` as the publishing source.

* visit site at `<GITHUB_USERNAME>.github.io/<REPO_NAME>`.

* If repo name is `<GITHUB_USERNAME>.github.io/` url will be same.

## Manual Deploy

To deploy site anywhere you like, build the site first with 

```bash
JEKYLL_ENV=production bundle exec jekyll b
```

Upload the directory `_site` to your server.

## Deploy to CloudFlare Pages

* Login to Cloudflare, Select `pages` on the `Dashboard`
* If haven't connected to your git repo please do. 
* select repo and set vars
  * `Framework Preset` to `Jekyll`
  * `Build command` to `jekyll build`
  * `Build output directory` to `_site`
* Clcik `Save and Deploy` to deploy your site on CF's network
* url most likely would be(if it's unique enough) `<REPO_NAME>.pages.dev`

