
#### [Demos and Documentation](https://fusioncharts.github.io/angular4-fusioncharts/)

# Angular4-Fusioncharts

A simple and lightweight Angular4 component which provides bindings for FusionCharts JavaScript Charting Library. It easily adds rich and interactive charting to any Angular Projects.

## Installation

To install `Angular4-FusionCharts` library, run:

```bash
$ npm install angular4-fusioncharts --save
```

Also install `FusionCharts` library if it is not already installed:

```bash
$ npm install fusioncharts --save
```

## Getting Started

After installing `angular4-fusioncharts`, import it in your Angular `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import * as FusionCharts from 'fusioncharts';
import * as Charts from 'fusioncharts/fusioncharts.charts';
import * as FintTheme from 'fusioncharts/themes/fusioncharts.theme.fint';

import { AppComponent } from './app.component';
import {
    FusionChartsModule,
    FusionChartsComponent,
    FusionChartsService,
    FusionChartsCoreService
} from 'angular4-fusioncharts';

@NgModule({
    declarations: [
        AppComponent
    ],
    imports: [
        BrowserModule,
        FusionChartsModule.forRoot(FusionCharts, Charts, FintTheme)
    ],
    providers: [],
    bootstrap: [AppComponent]
})
export class AppModule { }
```

Once the library is imported, you can use this component in your Angular application:

In your Angular `AppComponent`:

```typescript
import { Component } from '@angular/core';

@Component({
    selector: 'app-root',
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
})
export class AppComponent {
    id = 'chart1';
    width = 600;
    height = 400;
    type = 'column2d';
    dataFormat = 'json';
    dataSource;
    title = 'Angular4 FusionCharts Sample';

    constructor() {
        this.dataSource = {
            "chart": {
                "caption": "Harry's SuperMart",
                "subCaption": "Top 5 stores in last month by revenue",
                "numberprefix": "$",
                "theme": "fint"
            },
            "data": [
                {
                    "label": "Bakersfield Central",
                    "value": "880000"
                },
                {
                    "label": "Garden Groove harbour",
                    "value": "730000"
                },
                {
                    "label": "Los Angeles Topanga",
                    "value": "590000"
                },
                {
                    "label": "Compton-Rancho Dom",
                    "value": "520000"
                },
                {
                    "label": "Daly City Serramonte",
                    "value": "330000"
                }
            ]
        }
    }
}
```

You can now use `fusioncharts` component in your `app.component.html` template:

```html
<h1>
  {{title}}
</h1>
<fusioncharts
    [id]="id"
    [width]="width"
    [height]="height"
    [type]="type"
    [dataFormat]="dataFormat"
    [dataSource]="dataSource"
></fusioncharts>
```

## Contributing

* Clone the repository.
* Install dependencies
* Run `npm start` to start the dev server.
* Open `http://localhost:4200/` in your browser.

```sh
$ git clone https://github.com/fusioncharts/angular4-fusioncharts.git
$ cd angular4-fusioncharts
$ npm i
$ npm start
```
To build, run:

```sh
$ npm run build
```

### [Demos and Documentation](https://fusioncharts.github.io/angular4-fusioncharts/)