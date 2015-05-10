# Jerkll

A tiny(!) JavaScript clone of [Jekyll](http://jekyllrb.com/) inspired by
[RequireJS](http://requirejs.org/)

Like **Jekyll**, you maintain your website as a collection of static markdown
files. Like **RequireJS**, dependencies (templates) are resolved on the fly
via http.

No server-side compilation is need. All rendering is done in the browser.

## Is this a terrible idea?

Yes.

## Usage

* Install: Place the `index.html` file in the root of your web path.
* Create your pages as `.md` files. `/index.md` will be your default page.
* Link to other pages: `#path/to/markdown/file`.
* For local development, issue `python -m SimpleHTTPServer`. Asynchronous
  loading of files is prohibited via the `file:///` protocol.

### Format

Pages and templates take the following format:

      ---
      {
         "template": "templates/index.html",
         "name": "Captbaritone"
      }
      ---
      # Hello World

      My name is {{ name }}. Welcome to my home page, please visit my [blog](#blog)

A template must include a `{{ content }}` wild card:

      ---
      {
         "title": "Jerkll"
      }
      ---
      <title>{{ title }}</title>
      <h1>My Home Page</h1>

      <a href='#'>Home</a>
      {{ content }}
