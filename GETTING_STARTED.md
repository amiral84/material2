Get started with Angular Material 2 using the Angular CLI.

## Install the CLI
 
 ```bash
 npm install -g angular-cli
 ```
 
## Create a new project
 
 ```bash
 ng new my-project
 ```

The new command creates a project with a build system for your Angular app.

## Install Angular Material components 

```bash
npm install --save @angular/material
```

## Import the Angular Material NgModule
  
**src/app/app.module.ts**
```ts
import { MaterialModule } from '@angular/material';
// other imports 
@NgModule({
  imports: [MaterialModule.forRoot()],
  ...
})
export class PizzaPartyAppModule { }
```

## Map Angular Material in System config
This is **required** step, otherwise you will get an error from zonejs.
```js
System.config({
  defaultJSExtensions: true,
  paths: {
    'npm:': './'
  },
  map: {
    app: 'app',

    '@angular/core': 'npm:@angular/core/bundles/core.umd.js',
    '@angular/common': 'npm:@angular/common/bundles/common.umd.js',
    '@angular/compiler': 'npm:@angular/compiler/bundles/compiler.umd.js',
    '@angular/platform-browser': 'npm:@angular/platform-browser/bundles/platform-browser.umd.js',
    '@angular/platform-browser-dynamic': 'npm:@angular/platform-browser-dynamic/bundles/platform-browser-dynamic.umd.js',
    '@angular/http': 'npm:@angular/http/bundles/http.umd.js',
    '@angular/router': 'npm:@angular/router/bundles/router.umd.js',
    '@angular/forms': 'npm:@angular/forms/bundles/forms.umd.js',
    '@angular/material': 'npm:@angular/material/material.umd.js', //Add this line

    // other libraries
    'rxjs':                       'npm:rxjs'
  }
});
```

## Include the core and theme styles:
This is **required** to apply all of the core and theme styles to your application. You can either
use a pre-built theme, or define your own custom theme.

:trident:  See the [theming guide](docs/theming.md) for instructions.

### Additional setup for `md-slide-toggle` and `md-slider`:
The slide-toggle and slider components have a dependency on [HammerJS](http://hammerjs.github.io/).

Add HammerJS to your application via [npm](https://www.npmjs.com/package/hammerjs), a CDN 
(such as the [Google CDN](https://developers.google.com/speed/libraries/#hammerjs)), or served 
directly from your app.

### [Optional] Using Material Design icons with `md-icon`:

- If you want to use Material Design icons in addition to Angular Material components, 
load the Material Design font in your `index.html`.  
`md-icon` supports any font icons or svg icons, so this is only one option for an icon source.
       
**src/index.html**
```html
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

## Sample Angular Material 2 projects
- [Material 2 Sample App](https://github.com/jelbourn/material2-app)
- [Angular Connect 2016 Demo](https://github.com/kara/leashed-in)
