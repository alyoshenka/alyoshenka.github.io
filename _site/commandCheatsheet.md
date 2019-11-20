```bash
jekyll build // builds site, outputs to static directory _site
jekyll serve // same + rebuilds with every change + runs local web server
```

Liquid: templating language

    Objects: where to output content

        {{ page.title }}

    Tags: logic and control flow

        {% if page.show_sidebar %}

            // html

        {% endif %}

        include: include from file in _includes/

    Filters: change output of object

        {{ "hi" | capitalize }}

        ex. markdownify


    content (variable): value of rendered content on page 

    page.url: current url

Front Matter: YAML to set variables

    tells Jekyll to process Liquid

    ---

    my_number: 5

    ---



Layoout: template that wraps around content (if you add layout, content is auto populated)


    in _layouts/layoutName.html



posts: site.posts

    post.url: output path of post

    post.title: pulled from filename, overridden by setting {title} in front matter

    post.excerpt: first paragraph of content



Collection: similar to post, but content not grouped by data

    default = do not output a document page


        _config.yml

            output: true // override this ^



Document: item in a collection

    folder in /_{collection_name}



site.{collection_name} gets collection

    {% for author in site.authors %}

    // give them an author page

    {% endfor %}    



Gemfile: ensures version of Jekyll + other gems stays consistent

    bundle install: creates Gemfile.lock

Gemfile.lock: locks current gem versions, bundle update to update

    restricts Ruby environment to only use Gems in Gemfile

    // https://jekyllrb.com/docs/step-by-step/10-deployment/

    // when I'm ready for more advannced stuff ^






