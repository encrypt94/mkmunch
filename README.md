mkmunch
=======

Generate printable munchkin cards from YAML description and HTML+CSS template.

Probably you'll not like that ugly and incomplete tool. If you want something better look at:
Give a look to:
- [squib](https://squib.rocks/)
- [cider](https://github.com/oatear/cider)

Requirements
------------

Just do `gem install --user-install --no-doc liquid` and install `wkhtmltopdf`.

Usage
-----

Take a look to `deck.example.yml`

run rake: `rake generate[./deck.examlple.yml]`

Your cards will be available in `_cards`

Fonts
-----

Font is not bundled, you can download a munchkin-like font [here](https://fontsgeek.com/fonts/Quasimodo-Regular)
