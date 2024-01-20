# 🎉 <a href="https://agezao.github.io/confetti-js" target="_blank">Confetti Generator</a> 🎉

Easily Generate random confetti with javascript and make your design look cooler

<a href="https://www.npmjs.com/package/confetti-js"><img src="https://badge.fury.io/js/confetti-js.svg"></a>

## Demo 🚀

<a href="https://agezao.github.io/confetti-js" target="_blank">Demo</a> // <a href="https://agezao.github.io/confetti-js/examples" target="_blank">Examples</a>

## Why?

Have you ever seen that cool looking confetti on landing pages and above-the-fold content? We give you the power to create the same effect for free and without the hassle of having to design or code it from scratch.

## Installing/Using

### 📲 Download

- Using `npm`

  ```bash
    npm install confetti-js --save
  ```

- Direct download -> [click here](https://github.com/agezao/confetti-js/archive/master.zip)

### ➕ Add scripts

- The `classic` way

  ```html
  <script src="node_modules/confetti-js/dist/index.min.js"></script>
  ```

- ES6 module

  ```javascript
  // At the component you want to use confetti
  import ConfettiGenerator from 'confetti-js';
  ```

### 🤔 How to use it?

After installing the plugin(the topic above), just call-it passing your options:

#### html

```html
<canvas id="my-canvas"></canvas>
```

#### javascript

```javascript
var confettiSettings = { target: 'my-canvas' };
var confetti = new ConfettiGenerator(confettiSettings);
confetti.render();
```

You can also pass a canvas element as the target:

```javascript
var confettiElement = document.getElementById('my-canvas');
var confettiSettings = { target: confettiElement };
var confetti = new ConfettiGenerator(confettiSettings);
confetti.render();
```

### React

```jsx
React.useEffect(() => {
  const confettiSettings = { target: 'my-canvas' };
  const confetti = new ConfettiGenerator(confettiSettings);
  confetti.render();

  return () => confetti.clear();
}, []); // add the var dependencies or not
```

done!

## Options

| Attribute           | Description                                                                                                                                                                               | Example value            | Default value                                          |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ | ------------------------------------------------------ |
| _`target`_          | The Id tag or node of the canvas that will be used                                                                                                                                        | 'my-canvas'              | 'confetti-holder'                                      |
| _`max`_             | The number of props(confetti) to be rendered                                                                                                                                              | 11                       | 80                                                     |
| _`size`_            | Prop size                                                                                                                                                                                 | 1.8                      | 1                                                      |
| _`animate`_         | If the confetti should fall                                                                                                                                                               | false                    | true                                                   |
| _`respawn`_         | If the confetti should be recreated after going off-screen                                                                                                                                | false                    | true                                                   |
| _`clock`_           | The speed confetti fall                                                                                                                                                                   | 50                       | 25                                                     |
| _`props`_           | The type of props(confetti) that should be rendered. In addition to those listed in the default, there's a special "svg" type which requires further configuration and is detailed below. | ['circle', 'square']     | ['circle', 'square', 'triangle', 'line']               |
| _`colors`_          | The color to be rendered on the confetti. By default, RGB format inside an array.                                                                                                         | [[0,0,0], [255,255,255]] | [[165,104,246],[230,61,135],[0,199,228],[253,214,126]] |
| _`start_from_edge`_ | Whether the confettis should fall from the top of the screen (or should move up from the bottom)                                                                                          | true                     | false                                                  |
| _`width`_           | Canvas width                                                                                                                                                                              | 960                      | _window size_                                          |
| _`height`_          | Canvas height                                                                                                                                                                             | 767                      | _window height_                                        |
| _`rotate`_          | If set to `true`, SVG and squares will rotate while falling.                                                                                                                              | `true`                   | `false`                                                |

### Special SVG particle type

There is an extra special partical type ("prop") which allows you to render SVGs as confetti particles. For example:

```json
{
  "props": ["circle", "square", { "type": "svg", "src": "site/hat.svg" }]
}
```

You must specify the `type` and `src` properties. There are also a few other configuration properties available to SVG objects:

| Attribute  | Description                                                                                        | Example value | Default value |
| ---------- | -------------------------------------------------------------------------------------------------- | ------------- | ------------- |
| _`size`_   | Set the size of the SVG when it renders as a particle.                                             | `25`          | `15`          |
| _`weight`_ | The probability of this particle being rendered, where 1 is a regular weight, and 0.1 is uncommon. | `0.5`         | `1`           |

## API

Using the object generated by `new ConfettiGenerator()` is pretty easy, there're just two main methods actually.

| Method     | Description                                             |
| ---------- | ------------------------------------------------------- |
| _`render`_ | Render the confetti at the config `<canvas/>`           |
| _`clear`_  | Clear the `<canvas/>` where the confetti where rendered |

```javascript
var confetti = new ConfettiGenerator();
confetti.render();
//
confetti.clear();
```
