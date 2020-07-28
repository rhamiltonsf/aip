# Contributing

The Salesforce AIPs are maintained by the API Stewardship Committee, which
welcomes all forms of contributions to this project.

## Contributions

Whether you want to propose new standards or contribute code to our repository, there are multiple ways to get involved with the AIP project.

### Requesting or proposing AIPs

The purpose of AIPs is to provide clarity to engineers about API shape and
style so that our products can provide a consistent development experience
across services. When an engineer finds that a best practice is not defined in
the AIPs, they can best help Salesforce improve the standard by requesting or
submitting an AIP. As we standardize our AIPs we enable our engineers to
innovate faster, and push the boundaries of the use cases for APIs. Not every
circumstance is going to be covered by an AIP.

You do not have to be an AIP contributor, or a member of the API Stewardship
committee to participate in this process. If you see a need for a standard that
is not already defined in the AIPs, follow the instructions for [proposing an AIP][].

### Join the API Stewardship Committee

The API Stewardship Committee governs the common standard for Salesforce and helps organization level C4E teams maintain extensions of the Salesforce AIPs in their organizations. They meet bi-monthly to review API standard proposals, issues, and updates.

The API Stewardship Committee is open to all interested Salesforce employees. Contact the API Stewardship Committee on [Chatter][] for more information.

### Become an AIP Editor

[AIP editors][] are in charge of maintaining consistency in structure and voice across the Salesforce AIPs.

Editors are currently chosen by invitation only. However, anybody may draft and AIP as a proposal. The best way to be invited to join the AIP editors would be to draft AIPs in accordance to the [AIP style guide][aip style guide].

### Improve the AIP infrastructure

The AIP Infrastructure refers to the HTML, CSS, Liquid templates, and tooling
used to display the AIP Markdown files in the browser. If you see something
that you think could be improved, please create an [issue][] or a pull request
in the AIP repository.

Note that Salesforce AIPs are an extension of [aip.dev][]. Some fundamental
infrastructure changes may be better submitted there. Salesforce has a CLA with
Google allowing Salesforce employees to contribute to this project. If you
would like to be included in the CLA, reach out to the [Open Source Programs
Office][].

For more information on contributing to [aip.dev][], reach out to the API Stewardship Committee on [Chatter][].

## Development Environment

If you are contributing documentation (rather than samples) and want to be able
to view it in your browser, the easiest way to do so is to run the provided
development server.

We use [GitHub Pages][1] to make this documentation available, which uses
[Jekyll][2] under the hood.

If you have [Docker][3] installed, clone this repository and run the `serve.sh`
file at the root of the repository. This script does two things:

- It builds the provided Docker image (unless you already have it) and tags it
  as `aip-site`.
- It runs the `aip-site` image.

The Jekyll development server uses port 4000 by default; point your web browser
to `http://localhost:4000`, and you should see the site.

**Note:** After building the Docker image for the first time, you may
experience issues if Ruby dependencies change underneath you. If this happens,
remove your Docker image (`docker rmi aip-site`) and run `serve.sh` again.

### Arguments

Any arguments provided to `serve.sh` (or `docker run`) are forwarded to Jekyll.
Note that the Docker entrypoint automatically provides `--destination` and
`--host` arguments, and you should not change these. Additionally, changing
ports is not advised (call `docker run` yourself with a customized `-p` switch
if you need to use custom ports).

### Hot reloading

The Jekyll development server supports "hot reloading" (where local changes
will be automatically reflected in your browser without having to manually
reload). You can activate this by sending the `--livereload` flag (`-l` for
short) to `serve.sh`.

### Local Installation

It is possible to run the development server locally also. The general gist of
how to do so correctly is:

- Install [rbenv](https://github.com/rbenv/rbenv).
- Use rbenv to install an appropriate version of Ruby.
- `gem install bundler`
- `bundle install`

Once this is done, you can run `bundle exec jekyll serve` to run the
development server (as above, include `--livereload` to get automatic
reloading).

**Note:** The Jekyll default setup will write the static site in-place to the
`_site` subdirectory. (The Docker image redirects this to an arbitrary spot in
the image so as not to pollute the local disk.)

## Code reviews

All submissions, including submissions by project members, require review. We
use GitHub pull requests for this purpose. Consult
[GitHub Help](https://help.github.com/articles/about-pull-requests/) for more
information on using pull requests.

### Formatting

We use [prettier][4] to format Markdown, JavaScript, and (most) HTML, in order
to ensure a consistent style throughout our source. You can add prettier as a
plugin in most development environments.

<!-- prettier-ignore-start -->
[1]: https://pages.github.com/
[2]: https://jekyllrb.com/
[3]: https://docker.com/
[4]: https://prettier.io/
[aip.dev]: https://aip.dev
[aip style guide]: ./aip/0008.md
[open source programs office]: https://confluence.internal.salesforce.com/display/OPENSOURCE/Open+Source+Programs+Office
[proposing an AIP]: ./aip/0001.md#proposing-an-aip
[Chatter]: https://gus.lightning.force.com/lightning/r/CollaborationGroup/0F9B0000000LZe2KAG/view
[AIP editors]: ./aip/0001.md#editors
<!-- prettier-ignore-end -->
