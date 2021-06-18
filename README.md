# tutor-code-snippets

打开 VS Code 在插件市场搜索 “tutor-code-snippets” 或者点击 <https://marketplace.visualstudio.com/items?itemName=hijiangtao.tutor-code-snippets> 下载安装即可。

本插件针对常见的 HTML 片段、TypeScript 片段和 CSS 片段进行简化处理，方便从简单指令直接生成代码片段，代码片段中针对常用的定制化参数增加了 tabstop，请结合使用。

* HTML 部分主要包括各类 Angular template 语法，如 ng-container、ng-template、ngSwitch 等等；
* TypeScript 部分主要包含以下几部分内容
    1. 各类便利生成 RxJS 操作符的用法
    2. 从服务端拉取 `Page<T>` 类数据的 service 便利写法
    3. Angular 各类 Component 生成写法
    4. Angular Pipe、Service、Validator、Directive 生成写法
    5. Angular 生命周期钩子函数生成写法
    6. logic.x.subscribe()、toPromise() 等便利写法
* CSS 部分主要从 Focus 代码中抽取大家常见的一些写法，方便使用

以下为目录

- [通用](#--)
  * [t-td](#t-td)
- [1. HTML](#1-html)
  * [t-ngif](#t-ngif)
  * [t-ngifv](#t-ngifv)
  * [t-ngt](#t-ngt)
  * [t-ngife](#t-ngife)
  * [t-ngs](#t-ngs)
  * [t-style](#t-style)
  * [t-ngstyle](#t-ngstyle)
  * [t-ngf](#t-ngf)
  * [t-ngrl](#t-ngrl)
  * [t-ngc](#t-ngc)
- [2. TypeScript](#2-typescript)
  * [t-rxbehaviorgs](#t-rxbehaviorgs)
  * [t-rxbehavior](#t-rxbehavior)
  * [t-rxreplay](#t-rxreplay)
  * [t-rxfrom](#t-rxfrom)
  * [t-rxof](#t-rxof)
  * [t-rxevent](#t-rxevent)
  * [t-destroy](#t-destroy)
  * [t-getpagedatai](#t-getpagedatai)
  * [t-getpagedata](#t-getpagedata)
  * [t-compi](#t-compi)
  * [t-compr](#t-compr)
  * [t-compv](#t-compv)
  * [t-comp](#t-comp)
  * [t-pipe](#t-pipe)
  * [t-service](#t-service)
  * [t-oe](#t-oe)
  * [t-sub](#t-sub)
  * [t-trackby](#t-trackby)
  * [t-topromise](#t-topromise)
  * [t-validator](#t-validator)
  * [t-validatorfn](#t-validatorfn)
  * [t-asyncvalidatorfn](#t-asyncvalidatorfn)
  * [t-directive](#t-directive)
  * [t-directivecss](#t-directivecss)
  * [Angular 生命周期钩子函数 t-ng*](#angular----------t-ng-)
- [3. CSS](#3-css)
  * [t-theme](#t-theme)
  * [t-rgb](#t-rgb)
  * [t-rgba](#t-rgba)
  * [t-flex](#t-flex)
  * [t-absolute](#t-absolute)
- [4. TypeScript React](#4-typescript-react)
  * [t-rfce](#t-rfce)
  * [t-rus](#t-rus)
  * [t-rue](#t-rue)
  * [t-ructx](#t-ructx)
  * [t-rur](#t-rur)
  * [t-rucb](#t-rucb)
  * [t-rum](#t-rum)
  * [t-ruref](#t-ruref)

详细文档如下

## 通用

### t-td

```
// HTML
<!-- TODO:  -->

// TypeScript
// TODO: 

// CSS, SCSS
/* TODO:  */
```

## 1. HTML

### t-ngif

```
<ng-container *ngIf="data$ | async as data">
    
</ng-container>
```

### t-ngifv

```
<ng-container *ngIf="(data$ | async) === value">
    
</ng-container>
```

### t-ngt

```
<ng-template #tplName>
    TemplateContent
</ng-template>
```

### t-ngife

```
<ng-container *ngIf="TODO; else tplName">
    
</ng-container>
<ng-template #tplName>
    
</ng-template>
```

### t-ngs

```
<ng-container [ngSwitch]="conditionExpression">
    <ng-container *ngSwitchCase="expression">output</ng-container>
    <ng-container *ngSwitchDefault>output2</ng-container>
</ng-container>
```

### t-style

```
[style.property]="expression"
```

### t-ngstyle

```
[ngStyle]="{style: expression}"
```

### t-ngf

```
<ng-container *ngFor="let item of list; trackBy: item.id">
    
</ng-container>
```

### t-ngrl

```
[routerLink]="['/routePath']" routerLinkActive="router-link-active" 
```

### t-ngc

```
<ng-container ></ng-container>
```

## 2. TypeScript

### t-rxbehaviorgs

```
/* TODO: 数据流定义 */
behaviorName$ = new BehaviorSubject<string>(initialValue)

get behaviorName() {
     return this.behaviorName$;
}

set behaviorName(value: string) {
     this.behaviorName$.next(value);
}
```

### t-rxbehavior

```
/* TODO: 数据流定义 */
behaviorName$ = new BehaviorSubject<string>(initialValue)
```

### t-rxreplay

```
/* TODO: 数据流定义 */
behaviorName$ = new ReplaySubject<string>(1)
```

### t-rxfrom

```
from(object)
    .map(v => v)
    .filter(v => true)
    .subscribe(
        value => { console.log(value) },
        error => { console.log(error) },
        () => { console.log('complete') }
    );
```

### t-rxof

```
of(object)
    .map(v => v)
    .filter(v => true)
    .subscribe(
        value => { console.log(value) },
        error => { console.log(error) },
        () => { console.log('complete') }
    );
```

### t-rxevent

```
fromEvent(target,eventName)
    .map(v => eventName)
    .filter(v => true)
    .subscribe(
        value => { console.log(value) },
        error => { console.log(error) },
        () => { console.log('complete') }
    );
```

### t-destroy

```
private destroyed$ = new Subject<void>();

ngOnDestroy(): void {
    this.destroyed$.next();
    this.destroyed$.complete();
}
```

### t-getpagedatai

```
constructor(private http: HttpClient) {}

// 获取数据
getPageData(params: any): Observable<Page<any>> {
    return this.http.get<Page<any>>(`/tutor-focus-gateway/api`, {
        params: {
            ...params
        } as any
    });
}
```

### t-getpagedata

```
// 获取数据
getPageData(params: any): Observable<Page<any>> {
    return this.http.get<Page<any>>(`/tutor-focus-gateway/api`, {
        params: {
            ...params
        } as any
    });
}
```

### t-compi

```
import { Component, OnInit } from '@angular/core';

@Component({
    selector: 'selector-name',
    template: ``
})

export class NameComponent implements OnInit {
    constructor() { }

    ngOnInit() { }
}
```

### t-compr

```
import { Component } from '@angular/core';

@Component({
    selector: 'prefix-app',
    template: `
        <router-outlet></router-outlet>
        `
})
export class AppComponent { }
```

### t-compv

```
import { NG_VALUE_ACCESSOR, ControlValueAccessor } from '@angular/forms';
import { Component, Input, OnInit, forwardRef } from '@angular/core';

export const COMPONENT_NAME_VALUE_ACCESSOR: any = {
    provide: NG_VALUE_ACCESSOR,
    useExisting: forwardRef(() => ComponentNameComponent),
    multi: true
};

@Component({
    selector: 'selector-name',
    templateUrl: './name.component.html',
    styleUrls: ['./name.component.css'],
    providers: [COMPONENT_NAME_VALUE_ACCESSOR]
})
export class ComponentNameComponent implements OnInit, ControlValueAccessor {

    private _value: any;

    set value(value: any) {
        this._value = value;
        this.notifyValueChange();
    }

    get value(): any {
        return this._value;
    }

    onChange: (value) => {};
    onTouched: () => {};

    constructor() { }

    notifyValueChange(): void {
        if (this.onChange) {
            this.onChange(this.value);
        }
    }

    ngOnInit(): void {
        
    }

    writeValue(obj: any): void {
        this._value = obj;
    }

    registerOnChange(fn: any): void {
        this.onChange = fn;
    }

    registerOnTouched(fn: any): void {
        this.onTouched = fn;
    }

    setDisabledState(isDisabled: boolean): void {
    }
}
```

### t-comp

```
import { Component, OnInit } from '@angular/core';

@Component({
    selector: 'selector-name',
    templateUrl: 'name.component.html'
})

export class NameComponent implements OnInit {
    constructor() { }

    ngOnInit() { }
}
```

### t-pipe

```
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
    name: 'selector-name'
})

export class NamePipe implements PipeTransform {
    transform(value: any, ...args: any[]): any {
        
    }
}
```

### t-service

```
import { Injectable } from '@angular/core';

@Injectable({providedIn: 'root'})
export class ServiceNameService {
    constructor() { }
    
}
```

### t-oe

```
@Output() eventName = new EventEmitter<eventType>();
```

### t-sub

```
this.function
    .subscribe(arg => this.property = arg);
```

### t-trackby

```
trackBy(index: number, name: model): number {
  return name.id;
}
```


### t-topromise

```
this.logic.function
    toPromise()
    .then(arg => {
        this.property = arg;
    });
    .catch(error => {
        console.error(error);
    }
```

### t-validator

```
import { Directive } from '@angular/core';
import { NG_VALIDATORS, AbstractControl, Validator, ValidationErrors } from '@angular/forms';

@Directive({
    selector: '[validatorName][ngModel]',
    providers: [
        { provide: NG_VALIDATORS, useExisting: className, multi: true }
    ]
})

export class className implements Validator {
    validate(c: AbstractControl): ValidationErrors | null {
        if (valid) {
            return null;
        }

        return {
            validatorName: {
                valid: false
            }
        };
    }
}
```

### t-validatorfn

```
export const validator = (parameters: any): ValidatorFn =>
    (abstractControl: AbstractControl): ValidationErrors | null => {
        return null;
};
```

### t-asyncvalidatorfn

```
export const validator = (parameters: any): AsyncValidatorFn =>
    (abstractControl: AbstractControl): Promise<ValidationErrors | null> | Observable<ValidationErrors | null> => {
        return Promise.resolve(null);
    };
```

### t-directive

```
import { Directive } from '@angular/core';

@Directive({
    selector: 'app-Name',
})
export class NameDirective {
     
}
```

### t-directivecss

```
import { Directive, ElementRef, Input } from '@angular/core';

@Directive({
    selector: '[app-name]',
})
export class NameDirective {
    constructor(private elementRef: ElementRef) {}

    private name(value: string) {
        this.elementRef.nativeElement.style.proptery = value;
    }
}
```

### Angular 生命周期钩子函数 t-ng*

|生命周期|指令|
|---|---|
|Angular-Lifecycle-OnChanges-Hook|t-ngonchanges|
|Angular-Lifecycle-OnInit-Hook|t-ngoninit|
|Angular-Lifecycle-DoCheck-Hook|t-ngdocheck|
|Angular-Lifecycle-AfterContentInit-Hook|t-ngaftercontentinit|
|Angular-Lifecycle-AfterContentChecked-Hook|t-ngaftercontentchecked|
|Angular-Lifecycle-AfterViewInit-Hook|t-ngafterviewinit|
|Angular-Lifecycle-AfterViewChecked-Hook|t-ngafterviewchecked|
|Angular-Lifecycle-OnDestroy-Hook|t-ngondestroy|

举例，比如 `t-ngafterviewinit`

```
ngAfterViewInit(): void {
    //Called after ngAfterContentInit when the component's view has been initialized. Applies to components only.
    //Add 'implements AfterViewInit' to the class.
    
}
```

## 3. CSS

### t-theme

```
@import 'src/theme/theme';
```

### t-rgb

```
background-color: rgb(0, 0, 0)
```

### t-rgba

```
background-color: rgba(0, 0, 0, 1)
```

### t-flex

```
display: flex;
justify-content: flex-start;
align-items: center;
```

### t-absolute

```
position: absolute;
left: 0;
right: 0;
width: 10px;
height: 10px;
text-align: center;
```

## 4. TypeScript React

### t-rfce

```
import React from 'react'

function DemoComponent() {
    return (
        <div>
            
        </div>
    )
}

export default DemoComponent
```

### t-rus

```
const [state, setState] = useState<type>(initialState); 
```

### t-rue

```
useEffect(() => {
    effect
    return () => {
        cleanup
    }
}, [input])
```

### t-ructx

```
const context = useContext(contextValue)
```

### t-rur

```
const [state, dispatch] = useReducer(reducer, initialState, init)
```

### t-rucb

```
useCallback(
    () => {
        callback
    },
    [input],
)
```

### t-rum

```
useMemo(() => function, input)
```

### t-ruref

```
const ref = useRef(initialValue)
```

