# dubotics.github.io

## Overview

This layout of this website is built on top of [Twitter-Bootstrap][tb], and is generated 
using [Jekyll][jk].

[tb]: http://getbootstrap.com/
[jk]: http://jekyllrb.com/

## Build Instructions

Note: The following instructions were almost directly copied from Github's [instructions][gh] 
on setting up Jekyll. 

1.  Install [Ruby][rb] (version 1.9.3 or 2.0.0); possibly higher
2.  Install [Bundler][bn]: `gem install bundler`
3.  Install dependencies: `bundle install` (run this within the project folder)
4.  If you are running Windows, you may need to do the following due to a bug in the syntax         
    highlighter we use. This may be fixed in future versions of `pygments.rb`, so try this
    only if it continues to throw an error:
    
        gem uninstall pygments.rb --version "=0.5.2"
        gem install pygments.rb --version "=0.5.0"
        
[gh]: https://help.github.com/articles/using-jekyll-with-pages
[bn]: http://bundler.io/
[rb]: https://www.ruby-lang.org/en/

## Testing the website

1.  Build and serve the site: `jekyll serve --watch`. 
    1. This will automatically rebuild the website whenever any changes are made.
    2. You can hit `ctrl+c` to quit the process.
    2. If you modify `_config.yml`, then you must quit and restart the entire command.
3.  Navigate to `localhost:4000` in your web browser to locally view the website for 
    testing purposes.

## Deploy

To deploy, simply push all changes to the master branch on Github:

    git add -A
    git commit -m "Add commit message here"
    git push origin master
    
The website at [http://dubotics.github.io](http://dubotics.github.io) will automatically 
update. This usually happens instantaneously, but can take up to 10 minutes, if Github is 
being slower then usual.

Note: your web browser may cache the website, and continue displaying the old version.
To force it to reset, try holding shift and pressing the "refresh" button to force it 
to clear the cache.

## Configuration

This site can be configured by either modifying `_config.yml`, or by modifying the 
individual files themselves. 

The following can be configured by modifying `_config.yml`. Note that you MUST kill and 
restart the Jekyll service after each modification.

-   Plugin configuration
-   Site name, description, and url
-   Blog excerpt and pagination configuration
-   Navbar elements (name and page url)
-   Carousel/slideshow pictures and refresh rate
-   Photo gallery pictures and album titles
-   Meeting times and locations
  
Anything else not mentioned above can be tweaked by modifying the individual html files.

## Blog posts

All blogposts must start with the following conventions:

-   Be located within the `_posts` folder
-   Have a filename following the format `yyyy-mm-dd-title-here.md`, where the date is the 
    intended date of publication. For example, if we had a blog post named "How to build a robot"
    that was published in October 19, 2013, the name of file would be 
    `2013-10-10-how-to-build-a-robot.md`.
-   Follow the following format:

        ---
        title: Title here
        author: Alice
        category: general
        layout: blog-post
        ---
        
        This is the "excerpt" portion of the blog post. This portion serves as a hook to 
        entice readers to continue reading, and will be displayed whenever a short snippit of
        the blog is needed.
        
        <!--more-->
        
        The blog post continues after the excerpt marker above. This should be where most of 
        the content goes. 

Each blog post is split up into three distinct sections: the front-matter, the excerpt, and 
the main content.

### Front-matter

The front-matter contains metadata about the document. The `title` and `author` attributes 
can be set to anything. 

The `category` attribute should be set to one of the following:

-   general
-   arm-team
-   chassis-team
-   control-systems-team
-   robotics-anonymous

The `layout` attribute must ALWAYS be set to `blog-post`.

You can optionally include the attribute `code:true` if you want to include syntax-highlighted
code inside the blog post, and optionally include the attribute `math:true` if you want to 
render mathematical equations (note: you can also use both at the same time).

### Content

The excerpt and main content is separated by the `<!--more-->` marker. The excerpt is 
shown in blog summaries and the RSS feed. Both the excerpt and the main content is combined
and shown within the actual blog post.

The body of the post must be written using [Markdown][md].

[md]: http://daringfireball.net/projects/markdown/

### Code:

You can include syntax-highlighted code by doing so:

    ---
    title: Testing code
    author: Alice
    category: general
    layout: blog-post
    code: true
    ---
    
    Some code:
    
    ```java
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello world!");
        }
    }
    ```
    
    <!--more-->
    
    Some more code:
    
    ```python
    print "Hello world!"
    ```
    
    You can use inline code like so: `std::cout << "Hello world!" << std::endl`,
    but it won't be highlighted.
    
Syntax-highlighted blocks are marked with three backtick symbols, and the optionally the name
of the programming language used, and inline code is delineated with a single backtick.

### Math:

You can include math by doing so:

---
    title: Testing math
    author: Alice
    category: general
    layout: blog-post
    math: code
    ---
    
    This is an example of how to include mathematical equations in a page. 

    Here is the quadratic formula:

    <div>
    $$
        x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} \\
    $$
    </div>

    <!--more-->

    This formula will work, but make sure that <span>\\( a >  0\\)</span>.

    Here is a matrix:

    <div>
    $$
        A = \left[\begin{array}{ccc}
            1 & 2 & 3 \\
            4 & 5 & 6 \\
            7 & 8 & 9 \\
        \end{array}\right]
        \cdot
        \left[\begin{array}{ccc}
            1 & 0 & 0 \\
            0 & 1 & 0 \\
            0 & 0 & 1 \\
        \end{array}\right]
    $$
    </div>

    Here is a case expression:

    <div>
    $$
    f(x) = \left\{\begin{array}{ll}
            x^2 + 3      & \text{if } x < 0 \\
            0            & \text{if } x = 0 \\
            \frac{1}{x}  & \text{if } x > 0 \\
        \end{array}\right.
    $$
    </div>
  
Due to bugs, the syntax is more clunkier. Inline math is delineated with `<span>\\(` and
`\\)</span>`, and block math is delineated with `<div>$$` and `$$</div>`.

The language used to write mathematical questions is called [LaTeX][tex], and is rendered
using a Javascript library called [MathJax][mj].

[tex]: http://en.wikibooks.org/wiki/LaTeX/Mathematics
[mj]: http://www.mathjax.org/

