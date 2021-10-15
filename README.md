# wordpress-node
A set of core WordPress functionality re-implemented in Node.js using the MySQL2 package. Allows you to deal directly with your WordPress database and supports functionality such as inserting posts, attachments, taxonomy terms and more.

# What?

One of the first questions I had when I told people about this, was: how is this any different to [Node WPApi](https://github.com/WP-API/node-wpapi)? The Node WP API package is great if you're working with a WordPress site and you're happy to use the REST API that WordPress provides. However, in performance-critical applications, the WordPress REST API suffers from numerous performance limitations that make it unviable in some situations.

What WordPress Node does is offers core WordPress functionality such as `wp_insert_post` and many other core functions, allowing you to easily perform actions on your WordPress database and side-step WordPress completely.

# The motiviation

The reason this library exists is because of a particular use-case I had with WordPress. I needed to download and insert data in a real-time fashion into WordPress. Sadly, PHP isn't a language that lends itself very well to parallel processing nor long-runing scripts. These things can be sorted, but they're a pain.

I had some scripts that were using numerous WordPress core functions out of convenience, but came at the expense of including the entire WordPress environment (plugins, themes and the core itself). WordPress Node is akin to a thin database client that handles all of the complex queries (a lot of JOIN's) associated with some of these WordPress functions.
