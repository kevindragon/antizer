# antizer

Antizer is a ClojureScript library implementing [Ant Design](https://ant.design/) React components for [Reagent](https://github.com/reagent-project/reagent) and [Rum](https://github.com/tonsky/rum).

Ant Design is an enterprise-class UI design language and React-based implementation with the following features:

* An enterprise-class UI design language for web applications.
* A set of high-quality React components out of the box.
* Extensive API documentation and examples.

## Resources

* [Reagent Demo](https://priornix.github.io/antizer/latest/examples/reagent.html)

* [Rum Demo](https://priornix.github.io/antizer/latest/examples/rum.html)

* [Antizer Documentation](https://priornix.github.io/antizer/latest/)

* [API Documentation](https://priornix.github.io/antizer/latest/api/)

* [Ant Design Component Documentation](https://ant.design/docs/react/introduce)

## Status

All the Ant Design components should be fully functional and production-ready. If you discover any missing or invalid components, please file a ticket.

### Who's Using Antizer

Please let me know if you are using Antizer within your project, and I will gladly add that in here.

## Usage

To use Antizer, add the following to your project.clj:

```clojure
[antizer "0.3.0"]
```

You would also need to add the ClojureScript React library that you will be using.

For Reagent:
```clojure
[reagent "X.Y.Z"]
```

For Rum:
```clojure
[rum "X.Y.Z"]
```

It is also necessary to include the Ant Design CSS stylesheet in your HTML page. The CSS files can be obtained from the following classpaths:

* `cljsjs/antd/development/antd.inc.css`
* `cljsjs/antd/production/antd.min.inc.css`

You can also follow the instructions for customization with LESS [here](https://ant.design/docs/react/customize-theme).

### Quick Example

For Reagent:
```clojure
(require '[antizer.reagent :as ant])
(require '[reagent.core :as r])

(defn render []
  [ant/button {:on-click #(ant/message-info "Hello Reagent!")} "Click me"])

(defn init! []
  (r/render [render] (.-body js/document)))
```

For Rum:
```clojure
(require '[antizer.rum :as ant])
(require '[rum.core :as rum])

(defn render []
  (ant/button {:on-click #(ant/message-info "Hello Rum!")} "Click me"))

(defn init! []
  (rum/mount (render) (.-body js/document)))
```

## Examples

To compile the examples:

```bash
lein with-profile +examples cljsbuild once
```

To compile the examples and enable hot reloading with figwheel:

```bash
lein with-profile +examples-dev figwheel
```

After compilation, open up the respective HTML page in the `examples/resources` folder in your browser.

## Changes

### 0.3.0
* Updated antd library to [3.7.1](https://ant.design/changelog#3.7.1). [#16](https://github.com/priornix/antizer/pull/16) thx [@sctianwei](https://github.com/sctianwei), [@piotr-yuxuan](https://github.com/piotr-yuxuan)
* Fixed autocomplete example for empty string.
* Fixed layout issue in examples.
* Removed known issue for DatePicker and Calendar components.
* Added props argument to reagent.create-form. [#12](https://github.com/priornix/antizer/pull/12)
thx [@AndreasKlein](https://github.com/AndreasKlein)
* Added Card.Meta example.

### 0.2.2
* Updated antd library to [2.12.3](https://ant.design/changelog#2.12.3).
* Fixed resource typo in README.md and documentation. [#1](https://github.com/priornix/antizer/issues/1) thx [@weavejester](https://github.com/weavejester)
* Added missing component: Breadcrumb.Item. [#2](https://github.com/priornix/antizer/issues/2) thx [@weavejester](https://github.com/weavejester)
* Added new component: Input.TextArea. [#3](https://github.com/priornix/antizer/issues/3) thx [@mbuczko](https://github.com/mbuczko)
* Fixed layout issue in examples.
* Added note on DatePicker and Calendar known issues.

### 0.2.1
* Updated antd library to [2.11.2](https://ant.design/changelog#2.11.2).
* Updated instructions for CSS file inclusion.
* Added Avatar component and example.
* Fixed layout and CSS styles for examples.
* Fixed cljsbuild settings for examples.

## Known Issues

None

## Acknowledgement

Thanks to Ant Design, [cljsjs/antd](https://github.com/cljsjs/packages/tree/master/antd), [Reagent](https://github.com/reagent-project/reagent), [Rum](https://github.com/tonsky/rum) and of course [ClojureScript](https://clojurescript.org), without which this project would not be possible.

## License

Copyright © 2017 Michael Lim

Licensed under Eclipse Public License (see LICENSE).
