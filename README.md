# terminal-site

**A portfolio you operate with a keyboard.**

Live site: **https://main.d397xzdpxm3z29.amplifyapp.com**

## The creative feature

The hero of the site is a working shell. Visitors can learn about me by typing commands, or tap the buttons on mobile.

| Command | What it does |
| --- | --- |
| `help` | Lists every command |
| `about` | Who I am |
| `skills` | What I work with |
| `projects` | Lists my projects |
| `open <name>` | Details and source link, for example `open pushtodeploy` |
| `deploy` | Replays a CI/CD pipeline ending at this very site |
| `contact` | Email, LinkedIn, Medium, Hashnode |
| `theme` | Cycles the color theme |
| `sudo hire-me` | A hidden command |

## The game layer

The site tracks XP as you explore. Eight achievements are hidden in normal use: run your first command, collect a superpower, ship a deploy, open a project, change the theme, reach out, run `sudo hire-me`, and scroll to the projects. Your level climbs from Visitor to DevOps Legend, and progress is saved in your browser.

Arrow keys recall earlier commands and Tab completes them.

## How it is built and deployed

```
git push  -->  GitHub (main)  -->  AWS Amplify Hosting  -->  CloudFront CDN  -->  visitor
```

| AWS service | Role |
| --- | --- |
| Amplify Hosting | Builds and serves the site, redeploys on every push to `main` |
| CloudFront | Global content delivery behind Amplify |
| Certificate Manager | HTTPS certificate for the Amplify URL |
| IAM | Service role that lets Amplify read the repo and deploy |

## Design decisions

- **One file.** `index.html` holds the markup, styles and script. There is no build step, so a push is a deploy.
- **No frameworks.** The terminal is plain JavaScript driven by a small command table.
- **Accessible by default.** Keyboard focus is visible, the terminal announces output to screen readers, and animation stops for users who prefer reduced motion.
- **Glassmorphism.** Frosted panels sit over slowly drifting color orbs, built with CSS backdrop filters and no images.
- **Mobile first.** Command buttons replace typing on small screens.

## Run it locally

Open `index.html` in any browser. Nothing to install.

## License

MIT. See [LICENSE](LICENSE).

## Author

Prachi Satbhai

[GitHub](https://github.com/prachi-satbhai0741) | [LinkedIn](https://www.linkedin.com/in/prachi-satbhai-2b8246322) | [Medium](https://medium.com/@prachisatbhai) | [Hashnode](https://hashnode.com/@prachisatbhai)
