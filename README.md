<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Boston House Prices

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> A (corrected) dataset derived from information collected by the US Census Service concerning housing in Boston, Massachusetts (1978).



<section class="usage">

## Usage

```javascript
import dataset from 'https://cdn.jsdelivr.net/gh/stdlib-js/datasets-harrison-boston-house-prices-corrected@esm/index.mjs';
```

#### dataset()

Returns a (corrected) dataset derived from information collected by the US Census Service concerning housing in Boston, Massachusetts (1978).

```javascript
var data = dataset();
/* returns
    [
        {
            'crim': 0.00632,
            'zn': 18.00,
            'indus': 2.310,
            'chas': 0,
            'nox': 0.5380,
            'rm': 6.5750,
            'age': 65.20,
            'dis': 4.0900,
            'rad': 1,
            'tax': 296.0,
            'ptratio': 15.30,
            'b': 396.90,
            'lstat': 4.98,
            'medv': 24.00,
            'cmedv': 24.00
        },
        ...
    ]
*/
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The data consists of 15 attributes:

    -   **crim**: per capita crime rate by town
    -   **zn**: proportion of residential land zoned for lots over 25,000 square feet
    -   **indus**: proportion of non-retail business acres per town
    -   **chas**: Charles River dummy variable (`1` if tract bounds river; `0` otherwise)
    -   **nox**: nitric oxides concentration (parts per 10 million)
    -   **rm**: average number of rooms per dwelling
    -   **age**: proportion of owner-occupied units built prior to 1940
    -   **dis**: weighted distances to five Boston employment centers
    -   **rad**: index of accessibility to radial highways
    -   **tax**: full-value property-tax rate per $10,000
    -   **ptratio**: pupil-teacher ratio by town
    -   **b**: `1000(Bk-0.63)^2` where `Bk` is the proportion of blacks by town
    -   **lstat**: percent lower status of the population
    -   **medv**: median value of owner-occupied homes in $1000's
    -   **cmedv**: corrected median value of owner-occupied homes in $1000's

-   The dataset can be used to predict two dependent variables: 1) nitrous oxide level and 2) median home value.

-   The median home value field seems to be censored at `50.00` (corresponding to a median value of $50,000). Censoring is suggested by the fact that the highest median value of exactly $50,000 is reported in 16 cases, while 15 cases have values between $40,000 and $50,000. Values are rounded to the nearest hundred. Harrison and Rubinfeld do not, however, mention any censoring.

-   The dataset contains eight corrections to miscoded median values, as documented by [Gilley and Pace (1996)][@gilley:1996a].

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import Plot from 'https://cdn.jsdelivr.net/gh/stdlib-js/plot@esm/index.mjs';
import dataset from 'https://cdn.jsdelivr.net/gh/stdlib-js/datasets-harrison-boston-house-prices-corrected@esm/index.mjs';

var data;
var plot;
var opts;
var x;
var y;
var i;

data = dataset();

// Extract housing data...
x = [];
y = [];
for ( i = 0; i < data.length; i++ ) {
    x.push( data[ i ].rm );
    y.push( data[ i ].cmedv );
}

// Create a plot instance:
opts = {
    'lineStyle': 'none',
    'symbols': 'closed-circle',
    'xLabel': 'Average Number of Rooms',
    'yLabel': 'Corrected Median Value',
    'title': 'Number of Rooms vs Median Value'
};
plot = new Plot( [ x ], [ y ], opts );

// Render the plot:
console.log( plot.render( 'html' ) );

</script>
</body>
</html>
```

</section>

<!-- /.examples -->



* * *

<section class="references">

## References

-   Harrison, David, and Daniel L Rubinfeld. 1978. "Hedonic housing prices and the demand for clean air." _Journal of Environmental Economics and Management_ 5 (1): 81–102. doi:[10.1016/0095-0696(78)90006-2][@harrison:1978a].
-   Gilley, Otis W., and R.Kelley Pace. 1996. "On the Harrison and Rubinfeld Data." _Journal of Environmental Economics and Management_ 31 (3): 403–5. doi:[10.1006/jeem.1996.0052][@gilley:1996a].

</section>

<!-- /.references -->

<!-- <license> -->

## License

The data files (databases) are licensed under an [Open Data Commons Public Domain Dedication & License 1.0][pddl-1.0] and their contents are licensed under a [Creative Commons Zero v1.0 Universal][cc0]. The software is licensed under [Apache License, Version 2.0][apache-license].

<!-- </license> -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/datasets-harrison-boston-house-prices`][@stdlib/datasets/harrison-boston-house-prices]</span><span class="delimiter">: </span><span class="description">A dataset derived from information collected by the US Census Service concerning housing in Boston, Massachusetts (1978).</span>
-   <span class="package-name">[`@stdlib/datasets-pace-boston-house-prices`][@stdlib/datasets/pace-boston-house-prices]</span><span class="delimiter">: </span><span class="description">A (corrected) dataset derived from information collected by the US Census Service concerning housing in Boston, Massachusetts (1978).</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## Copyright

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/datasets-harrison-boston-house-prices-corrected.svg
[npm-url]: https://npmjs.org/package/@stdlib/datasets-harrison-boston-house-prices-corrected

[test-image]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/actions/workflows/test.yml/badge.svg?branch=v0.2.1
[test-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/actions/workflows/test.yml?query=branch:v0.2.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/datasets-harrison-boston-house-prices-corrected/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/datasets-harrison-boston-house-prices-corrected?branch=v0.2.1

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/datasets-harrison-boston-house-prices-corrected.svg
[dependencies-url]: https://david-dm.org/stdlib-js/datasets-harrison-boston-house-prices-corrected/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[cli-section]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected#cli
[cli-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/tree/cli
[@stdlib/datasets-harrison-boston-house-prices-corrected]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/tree/main

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/tree/deno
[deno-readme]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/tree/umd
[umd-readme]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/tree/esm
[esm-readme]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices-corrected/blob/main/branches.md

[@harrison:1978a]: https://doi.org/10.1016/0095-0696%2878%2990006-2

[@gilley:1996a]: https://doi.org/10.1006/jeem.1996.0052

[csv]: https://tools.ietf.org/html/rfc4180

[ndjson]: http://specs.frictionlessdata.io/ndjson/

[pddl-1.0]: http://opendatacommons.org/licenses/pddl/1.0/

[cc0]: https://creativecommons.org/publicdomain/zero/1.0

[apache-license]: https://www.apache.org/licenses/LICENSE-2.0

<!-- <related-links> -->

[@stdlib/datasets/harrison-boston-house-prices]: https://github.com/stdlib-js/datasets-harrison-boston-house-prices/tree/esm

[@stdlib/datasets/pace-boston-house-prices]: https://github.com/stdlib-js/datasets-pace-boston-house-prices/tree/esm

<!-- </related-links> -->

</section>

<!-- /.links -->
