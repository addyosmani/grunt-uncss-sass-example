grunt-uncss-sass-example
========================

An example of using grunt-uncss on a simple multi-page Sass project.

## Usage

Clone the repository and install necessary dependencies:

```
$ git clone https://github.com/addyosmani/grunt-uncss-sass-example.git
$ cd grunt-uncss-sass-example
$ npm install && bower install
```

Run one of the available build tasks.

```
$ grunt
```

will build a version of the project *without* unused CSS removed. By default the stylesheet this produces is ~95KB.

```
$ grunt build-uncss
```

will build a version *with* unused CSS removed. The stylesheet produced by this build is ~13KB.

## Notes

The initial app was generated using Yeoman's `generator-webapp` and includes all the necessary tasks for Sass/Compass compilation, watching and optimization.

The most important point worth noting is that `grunt-uncss` is run at the very *end* of your build process here, ensuring all preprocessor tasks have had their chance to complete. This works fine for me.

You can run uncss earlier on in the build if you want, but will need to take care of pointing your `usemin` blocks to the correct final destination of your CSS files, as they will otherwise point to where it expects your Sass files to go. Something like `grunt-processhtml` can be used here if required.

## License

(C) Addy Osmani 2014, released under an MIT license