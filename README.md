# Brewscribe

Brewscribe is a Beersmith2 (.bsmx) file parser.

## Installation

`gem install brewscribe` or `gem brewscribe` in your Gemfile.

## Usage

To start, you can import your .bsmx file with `Brewscribe.import(file)` where file
is any object that responds to `#read`.  This will return an array of Brewscribe::Recipe
objects.  You now have a parsed version of the recipe files.

By default, Brewscribe will set a text property for each attribute of the recipe, and
if it has a parser object it will attempt to further parse the data.

An example of this is found in `Brewscribe::IngredientList`:

```
recipe = Brewscribe.import File.read './spec/support/recipe.bsmx'
recipe.ingredients.class # => Brewscribe::IngredientList
recipe.ingredients.grains.class # => Array
recipe.ingredients.grains.first.class # => Brewscribe::Grain
recipe.ingredients.grains.first.name # => "Pale Malt (2 Row) US"
```

## Contributing

I <3 Contributions.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Author

Created by [Andrew Nordman](https://github.com/cadwallion/).
