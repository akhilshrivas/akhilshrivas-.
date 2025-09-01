name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *" # every 12 hours
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v2

      - name: Generate snake animation
        uses: Platane/snk@master
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
