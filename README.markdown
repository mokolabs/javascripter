Javascripter
============

Javascripter is a Rails plugin that helps keep your javascript files organized.


Status
------

This plugin is no longer supported (mainly because I'm no longer actively using it). It should run well in Rails 2.3.X, but may not be compatible with Rails 3. If you're interested in taking over this project, please let me know. Alternately, if you have useful patches, send me a pull request and I will apply them -- but, otherwise, I have no personal plans for future development on this plugin.


Install
-------

To install, just add Javascripter to your `vendor/plugins` directory:

    script/plugin install git://github.com/mokolabs/javascripter.git
    

Usage
-----

To use Javascripter, replace your `javascript_include_tags` with a single tag:

    <head>
    <title>the.rails.ist</title>
    <%= javascripts %>
    </head>

Once you do, your javascripts will be included automatically, using the conventions below.

    <head>
    <title>the.rails.ist</title>
    <script src="/javascripts/application.js?1183566571" />
    </head>


Organize your javascripts
-------------------------

Javascripter uses a simple set of conventions:

- Javascript for your entire application should be stored in `application.js`
- Javascript for specific controllers should be stored in `controller.js`
- Javascript for specific actions should be stored in `controller_action.js`
- Javascript for specific actions should be stored in `controller/action.js` (optional)

Follow these conventions and Javascripter will reward you with automagic goodness, loading javascripts for specific controllers or actions whenever they are active.

Support for :defaults
---------------------

Need Prototype? Just use the `:defaults` parameter, like normal.

    <%= javascripts :defaults %>


Include additional javascripts
------------------------------

Need to include extra javascript libraries? Use the `:include` parameter:

    <%= javascripts :include => "lowpro" %>
    <%= javascripts :include => ["lowpro", "lightbox"] %>


Generator
---------

Javascripter also includes a generator that will create a default `application.js` script and separate javascript files for each controller in your application.

To use the generator, run this command in your terminal:

    script/generate javascripts

If you add a new controller, just run the generator again and a new javascript for the controller will be created. (Existing javascripts will be ignored.)


Credits
-------

Special thanks to [Lachie Cox](http://blog.smartbomb.com.au) and the rest of my [RORO Sydney](http://rubyonrails.com.au/sydney-meetups) comrades who asked for this plugin.


Feedback
--------

Comments and patches welcome at [http://github.com/mokolabs/javascripter/](http://github.com/mokolabs/javascripter/).
