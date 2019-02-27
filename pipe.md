
### Angular pipes  
A way to write display-value transformations that you can declare in your HTML.

A pipe takes in data as input and transforms it to a desired output.

#### Built-in pipes: 

```
DatePipe, UpperCasePipe, LowerCasePipe, CurrencyPipe, and PercentPipe. 
```

#### Custom pipes:
```
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({name: 'exponentialStrength'})
export class ExponentialStrengthPipe implements PipeTransform {
  transform(value: number, exponent: string): number {
    let exp = parseFloat(exponent);
    return Math.pow(value, isNaN(exp) ? 1 : exp);
  }
}
```

This pipe definition reveals the following key points:

A pipe is a class decorated with pipe metadata.
The pipe class implements the PipeTransform interface's transform method that accepts an input value followed by optional parameters and returns the transformed value.
There will be one additional argument to the transform method for each parameter passed to the pipe. Your pipe has one such parameter: the exponent.
To tell Angular that this is a pipe, you apply the @Pipe decorator, which you import from the core Angular library.
The @Pipe decorator allows you to define the pipe name that you'll use within template expressions. It must be a valid JavaScript identifier. Your pipe's name is exponentialStrength.

transform :  Technically, it's optional; - Angular looks for and executes the transform method regardless.

You must include your pipe in the declarations array of the AppModule.


# Pure and impure pipes
Angular executes a pure pipe only when it detects a pure change to the input value. 
A pure change is either a change to a primitive input value (String, Number, Boolean, Symbol) or a changed object reference (Date, Array, Function, Object).

Angular executes an impure pipe during every component change detection cycle. An impure pipe is called often, as often as every keystroke or mouse-move.
```
@Pipe({
  name: 'flyingHeroesImpure',
  pure: false
})
```

The Angular AsyncPipe is an interesting example of an impure pipe. The AsyncPipe accepts a Promise or Observable as input and subscribes to the input automatically, eventually returning the emitted values.

The AsyncPipe is also stateful. The pipe maintains a subscription to the input Observable and keeps delivering values from that Observable as they arrive.

This next example binds an Observable of message strings (message$) to a view with the async pipe.




