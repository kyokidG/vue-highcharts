# vue-highcharts

[![NPM version](https://img.shields.io/npm/v/vue-highcharts.svg)](https://www.npmjs.com/package/vue-highcharts)
[![License](https://img.shields.io/npm/l/vue-highcharts.svg)](https://github.com/weizhenye/vue-highcharts/blob/master/LICENSE)

Highcharts component for Vue.

## Installation

```bash
npm i vue-highcharts -S
```

## Usage

You should always call the `Vue.use()` global method:

```js
import Vue from 'vue';
import VueHighcharts from 'vue-highcharts';

Vue.use(VueHighcharts);
```

If you want to use Highstock, Highmaps or any other add-ons, you should pass in the `Highcharts` object [which included the corresponding modules](http://www.highcharts.com/docs/getting-started/install-from-npm).

```js
// Use Highstock
import Vue from 'vue';
import VueHighcharts from 'vue-highcharts';
import Highcharts from 'highcharts/highstock';

Vue.use(VueHighcharts, { Highcharts });
```

```js
// Use Highstock and Highmaps
import Vue from 'vue';
import VueHighcharts from 'vue-highcharts';
import Highcharts from 'highcharts/highstock';
import loadMap from 'highcharts/modules/map';

loadMap(Highcharts);

Vue.use(VueHighcharts, { Highcharts });
```

Then you can use the components in your template.

```html
<highcharts :options="options"></highcharts>
<highstock :options="options"></highstock>
<highmaps :options="options"></highmaps>
<highcharts-renderer :width="width" :height="height"></highcharts-renderer>
```

The `options` object can be found in [Highcharts API Reference](http://api.highcharts.com/highcharts).

`<highcharts-renderer>` [creates an independent renderer](http://api.highcharts.com/highcharts/Renderer).

The `Highcharts` object is available at `vm.Highcharts`. If you want to access the `chart` or `renderer` instance, you can use child component refs:

```html
<highcharts :options="options" ref="highcharts"></highcharts>
<highcharts-renderer :width="width" :height="height" ref="highchartsRenderer"></highcharts-renderer>
```

```js
const { chart } = vm.$refs.highcharts;
const { renderer } = vm.$refs.highchartsRenderer;
```

## Demo

* [Access `chart` instance via refs](https://codepen.io/weizhenye/pen/rrKgbP)
* [Use Highmaps](https://codepen.io/weizhenye/pen/VKdJpW)
* [Use independent Renderer](https://codepen.io/weizhenye/pen/kkpKvY)
