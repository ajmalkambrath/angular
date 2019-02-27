### Angular 6

- Angular 6 is focussed less on the underline framework and more on toolings and making easier
- No major break down but it depends on Rxjs version 6 which come with major break down
- Synchronise version number for Angular Framework, cli, material and SDK.

# Animation
 Pre :  import form '@angular/core
 New :  import from '@angular/animations
 
# Removed support from <template> directive
   should be used : <ng-template>
   
# Registering Provider
  providedIn: 'root' - Helpfull in treeshakable
  ```
  @Injectable({
  providedIn: 'root'
})
```
  
# ngModelChange event
Pre: we will get old data for handler 
Now: updated value

Before Angular 6, the ngModelChange event was emitted before the said form control updating.
If we have an event handler for the ngModelChange event that checked the value through the control,
the old value will be returned instead of the changed value.
Now, in Angular 6, ngModelChange has emitted the value after the value is updated in the form control.

# Angular elements
- Ability to use angular component in other environment.

# Ivy
- New gen rendering engine

# Treeshaking
- unused code does not get used in our final bundle.

 
### Angular CLI update
 
# ng update <package>
  Analyses angular app give up package updation
  
# ng add
- to add new capabities
- ng add @angualar/material

# Renamed config file
- Support for multiple project
- angular.json instead of  angular-cli.json 

