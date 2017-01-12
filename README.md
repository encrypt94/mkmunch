mkmunch
=======

Generate printable munchkin cards from YAML description and HTML+CSS template.

Usage
-----

Create a deck.yml file

```yaml
layout: door
cards:
 - level: 0
   name: Noname
   special-cases: Sadness
   image: nopic
   bad-stuff: :/
   levels: 0
   treasures: 0
 - level: 1000
   name: Uber cool name
   special-cases: Everything is awesome!
   image: nopic
   bad-stuff: nope
   levels: 100
   treasures: 100
```
run rake: `rake generate[./deck.yml]`

Your cards will be available in `_cards`

Fonts
-----

You can download useful fonts [here](http://lepecorelle.altervista.org/altro/font/)
