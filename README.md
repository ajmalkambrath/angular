# angular

### API Call

```
1. import { HttpClientModule } from '@angular/common/http';
2. App.Module inside @NgModule() import HttpClientModule after BrowserModule.
3. import { HttpClient } from '@angular/common/http';
4. constructor(private http: HttpClient) { }
5. showConfig() {
  this.configService.getConfig()
    .subscribe( data => this.config = data );
}
6. getConfig() { return this.http.get(this.configUrl); }
7. 

```
