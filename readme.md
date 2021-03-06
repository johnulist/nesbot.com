# nesbot.com

I am making the source code of my [personal site](http://nesbot.com) available publicly in case it helps anybody. It's developed using the [Slim Framework](http://slimframework.com).

I am working on a blog post about the rewrite and it ~~should get posted in the next few days~~ finally got posted: [http://nesbot.com/2013/1/11/this-blog-trimmed-the-fat-now-powered-by-slim-2](http://nesbot.com/2013/1/11/this-blog-trimmed-the-fat-now-powered-by-slim-2).

## Installation

The dependencies are resolved using [composer](http://getcomposer.org/).

If you have PHP 5.4+ installed you can be up and running in 10 seconds +/- 5 seconds for slower typers or copy & pasters.

```
git clone git://github.com/briannesbitt/nesbot.com.git
cd nesbot.com
curl -s http://getcomposer.org/installer | php
php composer.phar update
touch env.local
cd public
php -S 127.0.0.1:80
```

Thats it. Open a browser to http://127.0.0.1/ and you should see the site as you see at [nesbot.com](http://nesbot.com)

If you are running a version of PHP 5.3, the setup for nginx and apache are shown below.  Either way you will still need to perform the first 5 commands from above.

### Nginx

http://docs.slimframework.com/pages/routing-url-rewriting/#nginx

The `root` should be pointing to the `/your/install/path/nesbot.com/public` directory of the project.

### Apache

http://docs.slimframework.com/pages/routing-url-rewriting/#apache_and_mod_rewrite

As shown you will need to create a `.htaccess` file in the 'public/' folder.  I try not to use apache if possible so there isn't one in the repo.

The `DocumentRoot` should be pointing to the `/your/install/path/nesbot.com/public` directory of the project.

## How do I?

### Bundle assets

To generate the posts file, compile the less and minify/combine the js run the following command from the project root.

`php bundle.php`

> This command is run on every page load when in local (development) mode.

### Add a post

* Create a new file in `views/posts/` with a format of `yyyy-m-d-slug.php`.
* The first line in the file needs to be `<?/*Post title!*/?>`.
* Run `php genposts.php` from the project root. (this is automatically ran when in local mode)

This will parse the files in the `views/posts/` directory and extract the date, slug and title for each post and generate a new `posts.php`.

See the posts already in there for examples of functions you can use while writing posts.

### What about... ?

This isn't your grandma's blog... read the code and figure it out.

## Author

Brian Nesbitt - <brian@nesbot.com> - <http://twitter.com/NesbittBrian>

## License

### Source code

The code for this project is licensed under the MIT License.

### Blog posts

You are free to copy, distribute, modify or display any or all of the blog post material. However you may not use it, in any way, for commercial purposes.

## Previous versions

Previously the site was developed against different versions of the Play framework.

* You can see the Playframework 1.2.3 repo here: https://github.com/briannesbitt/v1.nesbot.com
* You can see the Playframework BETA 2.0 repo here: https://github.com/briannesbitt/v2.nesbot.com