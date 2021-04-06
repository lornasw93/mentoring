# Install Bootstrap

Installing the 'bootsrap' package purely for it's css which we copy into the `angular.json` fil (see next step). `ng-bootstrap` for specific for Angular and doesn't require any JS. For more info [check here](https://ng-bootstrap.github.io/#/getting-started#installation).
```
ng add @ng-bootstrap/ng-bootstrap
npm i bootstrap
```

Add the following line in the `angular.json` file above the default styling file.
``` 
"styles": [
    "node_modules/bootstrap/dist/css/bootstrap.min.css", //✨
    "src/styles.less"
],
```

Install an additional package.
```
npm i @angular/localize
```

In the `polyfills.ts` add this line at the top.
```
import '@angular/localize/init';
```

Ensure the `NgbModule` is included in the `app.module.ts`. 
```
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { NgbModule } from '@ng-bootstrap/ng-bootstrap';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { ContactComponent } from './contact/contact.component';
import { NavbarComponent } from './shared/navbar/navbar.component';
import { FooterComponent } from './shared/footer/footer.component';

@NgModule({
  declarations: [
    AppComponent,
    HomeComponent,
    AboutComponent,
    ContactComponent,
    NavbarComponent,
    FooterComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    NgbModule //✨
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Run the project.
```
ng serve --o
```