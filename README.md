# email-style-guide
Treehouse's Email Style Guide

## Usage

```
@import email-style
```

TODO: Document on how to include this in other projects and 3rd-party email providers.

## Development

#### Setup

```
$ bin/setup
```

#### Start Jekyll

```
$ yarn serve
```

Now open: http://localhost:4000/email-style-guide/

#### Building Assets + Docs

Running `yarn serve` will automatically build assets when they change.  To build everthing, use:

```
$ yarn build
```

#### Clean Templates

If you ever remove templates, it's a good idea to clean-up the files generated `dist` and `docs` with:

```
$ yarn clean:templates
```

### Directory Structure

```
email-style-guide/
├── src/
│   ├── sass/
│   └── templates/
├── dist/
│    ├── css/
│    └── templates/
├── docs/
│   ├── src/
│   ├── assets/
│   └── templates/
```

#####  `src`

The `src` directory is where all source code is stored. Add new templates and styles here.

##### `dist`

The `dist` directory (short for distribution) is where all code is built. Running `yarn build` will generate CSS and HTML templates in this directory.

##### `docs`

The `docs` directory is where the style-guide documentation is stored.

##### `docs/assets`

The `docs/assets` directory is where all the style-guide documentation assets are stored.  Running `yarn build` will generate CSS and JavaScript in this directory.

##### `docs/templates`

Running `yarn build` will output templates to `docs/templates` as well for previewing.  In general you shouldn't add new templates here but instead add them under the `src` directory.

### Creating Templates

Add new templates to `src/templates`

**Building**

Build email templates with:

```
$ yarn build
```

**Previewing**

After you've added a template, you can preview it with Jekyll. Start the server if you haven't done so already:

```
$ yarn serve
```

Say you just added a template in: `src/templates/b2b/newsletter-08-2017.html`

Now open: http://localhost:4000/email-style-guide/templates/b2b/newsletter-08-2017.html and you should see a preview there.

## Testing

We use [HTMLProofer](https://github.com/gjtorikian/html-proofer) to check the documentation site + templates for broken links, missing images, invalid html, etc.

We currently run these HTMLProofer checks:

* [HtmlCheck](https://github.com/gjtorikian/html-proofer#html)
* [ImageCheck](https://github.com/gjtorikian/html-proofer#images)
* [LinkCheck](https://github.com/gjtorikian/html-proofer#links)
* [ScriptCheck](https://github.com/gjtorikian/html-proofer#scripts)

Setup the dependencies:

```
$ bin/setup
```

And then run:

```
$ yarn build && yarn test
```

Test individual templates:

```
$ bin/test src/templates/example.html
```

## Releasing

##### Update the release notes

Update `docs/release_notes.html` with the new version number and some notes about the release.

##### Bump the version number

Update the version number, create a git tag, and push.

```
$ yarn version
$ git push --tags
```
