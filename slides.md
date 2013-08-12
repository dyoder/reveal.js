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



### Jade

<pre><code data-trim>
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
</code></pre>



### DSLs For Markup

* No need for a new language
* Fully-featured (functions, loops, etc.)
* More naturally extensible



### JavaScript

<pre><code data-trim>
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
</code></pre>



### Uh, No

That's why we need Jade. Right?



### CoffeeScript

<pre><code data-trim>
@h1 "Jade - node template engine"
@div id: "container", class: "col", =>
  if youAreUsingJade is true
    @p "You are amazing"
  else
    @p "Get on it!"
  @p """
    Jade is a terse and simple
    templating language with a
    strong focus on performance
    and powerful features.
  """
</code></pre>



### SASS

<pre><code data-trim>
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
</code></pre>



### JavaScript

<pre><code data-trim>
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

this.mixins.rule.left = function(dist) {
  _this.float("left");
  return _this.marginLeft(dist);
};

this.rule("#data", function(_arg) {
  var left, tableBase;
  left = _arg.left, tableBase = _arg.tableBase;
  left("10px");
  return tableBase;
});
</code></pre>



### CoffeeScript

<pre><code data-trim>
@mixins.rule.tableBase = =>
  @rule "th", =>
    @textAlign "center"
    @fontWeight "bold"

  @rule "td, th", => 
    @padding "2px"

@mixins.rule.left = (dist) =>
  @float "left"
  @marginLeft dist

@rule "#data", ({left,tableBase}) =>
  left("10px")
  tableBase
</code></pre>
