## You Can't Do That &hellip;
### (In JavaScript)



<div style="display: inline-block; width: 70%">
## Me Me Me

Dan Yoder

Chief Panda

PandaStrike, LLC

<a href="mailto:dan@pandastrike.com">dan@pandastrike.com</a>

</div>
<img src="http://pandastrike.com/img/logo.png" style="width: 25%; border: none; display: inline-block"/>



<q>It's just syntactic sugar.</q>



### You say that &hellip;

Bonus points if you get the reference.



### Jade

    h1 Jade - node template engine
    #container.col
      if youAreUsingJade
        p You are amazing
      else
        p Get on it!
      p.
        Jade is a terse and simple
        templating language with a
        strong focus on performance
        and powerful features.



### DSLs For Markup

No need for a new language

Fully-featured (functions, loops, etc.)

More naturally extensible

Fast (no compilation)



### JavaScript

    var _this = this;

    this.h1("Jade - node template engine");

    this.div({
      id: "container",
      "class": "col"
    }, function() {
      if (true === youAreUsingJade) {
        _this.p("You are amazing");
      } else {
        _this.p("Get on it!");
      }
      return _this.p("Jade is a terse and simple\ntemplating language with a\nstrong focus on performance\nand powerful features.");
    });



### Uh, No

That's why we need Jade. Right?



### CoffeeScript

    @h1 "Nice - A component-oriented HCI framework in CoffeeScript"
    @div id: "container", class: "col", =>
      if youAreUsingNice is true
        @p "You are amazing"
      else
        @p "Get on it!"
      @p """
        Nice includes a terse and simple
        CoffeeScript DSL with a
        <del>strong focus on performance</del>
        [ed: it's already code]
        and powerful features.
      """



Let's try this with CSS.



### SASS

    @mixin table-base {
      th {
        text-align: center;
        font-weight: bold;
      }
      td, th {padding: 2px}
    }

    @mixin left($dist) {
      float: left;
      margin-left: $dist;
    }

    #data {
      @include left(10px);
      @include table-base;
    }



### JavaScript

    var _this = this;

    this.mixins.rule.tableBase = function() {
      _this.rule("th", function() {
        _this.textAlign("center");
        return _this.fontWeight("bold");
      });
      return _this.rule("td, th", function() {
        return _this.padding("2px");
      });
    };

    this.mixins.property.left = function(dist) {
      _this.float("left");
      return _this.marginLeft(dist);
    };

    this.context("#data", function(_arg) {
      var tableBase;
      tableBase = _arg.tableBase;
      _this.rule(function(_arg1) {
        var left;
        left = _arg1.left;
        return left("10px");
      });
      return tableBase;
    });



### CoffeeScript

    @mixins.rule.tableBase = =>
      @rule "th", =>
        @textAlign "center"
        @fontWeight "bold"

      @rule "td, th", => 
        @padding "2px"

    @mixins.property.left = (dist) =>
      @float "left"
      @marginLeft dist

    @context "#data", ({tableBase}) =>

      @rule ({left}) =>
        left("10px")

      tableBase



It's not that you **should** use DSLs.

It's that, in JavaScript, you **can't**.



The CoffeeScript NPM has 1,503 dependencies.

The **7th** most depended-upon module.



* Jade (680, 12th)
* Grunt (337, 27th)
* Stylus (335, 28th)
* Less (334, 29th)
* Handlebars (295, 33rd)



More than 15% of the top NPMs are DSLs.



CoffeeScript is expressive enough to replace them all.



That's more than syntactic sugar.

    P(CoffeeScript) > P(JavaScript)



### `Nice` on GitHub

https://github.com/pandastrike/nice