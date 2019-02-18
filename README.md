# Description
Load po files for use with `ngx-translate`

## Installation:

 ```
npm i @ngx-translate/core --save
npm i @fjnr/ngx-translate-po-http-loader --save
 ```

## Usage:
```ts
import { HttpClient, HttpClientModule } from '@angular/common/http';

import { TranslateModule, TranslateLoader } from '@ngx-translate/core';
import { TranslatePoHttpLoader } from '@fjnr/ngx-translate-po-http-loader';

export function createTranslateLoader(http: HttpClient) {
	return new TranslatePoHttpLoader(http, 'assets/i18n', '.po');
}

@NgModule({
	imports: [
		BrowserModule,
		HttpClientModule,
		TranslateModule.forRoot({
			loader: {
				provide: TranslateLoader,
				useFactory: createTranslateLoader,
				deps: [HttpClient]
			}
		})
	],
	bootstrap: [AppComponent]
})
export class AppModule { }
```

## Special thanks

This package is a fork of the [initial repository](https://github.com/biesbjerg/ngx-translate-po-http-loader) of [Kim Biesbjerg](https://github.com/biesbjerg). Special thanks to him for his effort in this project.
