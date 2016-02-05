# External Javascript Libraries In Rails

## Outline
Loading JavaScript into our application can be done many different ways in Rails. We can use HTML script tags for JS files located on another server. We can place third party JS files in our vendor folder. Finally we can even use gems to load the JS libraries we need. 

## External JavaScript
Not all of our JavaScript files will be loaded from our application directories. Sometimes we may want to load JS from a CDN. This can allow us to save on bandwidth and if we don't have a CDN setup for our application, it will help with file download speeds for users throughout the world. To load JS like this, we create HTML script tags in our application layout file.

```html
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" />
```

## Vendor Assets
Our applications will grow as we add more and more features. We might end up with a lot of different JS libraries along the way. The problem is all of these external JS files will need to be downloaded one by one and this will slow page load times. At some point, we will probably decide to have these external JS files to be internal JS files.

We don't really want to clutter our main assets/javascripts folder with code written and maintained by other people. This is why Rails provides the `vendor/assets/javascripts` folder. We can place third party JS libraries in here and add them to our JS manifest file. We also get the added benifit of having all of these external JS files combined into one file with all our application JS files.

## Gems
Manually adding JS to our vendor directory can be cumbersome and hard to maintain. New version of the JS files come out and unless we keeping track of every release, it's easy to fall behind. Luckly for us, many of the popular JS libraries we use have a gems. These gems package the JS files and when installed, add them to our asset path allowing us to require the JS inside of our manifest file.

For example, let's install the jQuery gem in our Gemfile. Once we `bundle install`, we are able to add `//= require jquery` to our manifest file. Now jQuery will be loaded by Rails. Plus, we can use bundler to update jQuery when new versions are released. Handling updating is particular helpful for bigger JS frameworks that might have many JS files and dependencies.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/external-javascript-libraries-in-rails' title='External Javascript Libraries In Rails'>External Javascript Libraries In Rails</a> on Learn.co and start learning to code for free.</p>
