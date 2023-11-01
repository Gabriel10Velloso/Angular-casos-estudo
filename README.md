# Card grid in Angular and CSS (2023 edition!)
````
👌 https://github.com/Gabriel10Velloso/angular-card-grid-css
https://www.youtube.com/watch?v=-80IDxbBxFs
````


# rapidapi https://rapidapi.com/hub

````
👌 https://rapidapi.com/hub
 Várias Apis para uso
````


# Medium

````
👌 Advanced Enum Techniques in Angular TypeScript Projects: Elevating Code Clarity
https://medium.com/@ayushgrwl365/advanced-enum-techniques-in-angular-typescript-projects-elevating-code-clarity-6b0a654fa29d


👌 Introducing Angular’s New Control Flow
https://stackblitz.com/edit/stackblitz-starters-dkoixf?file=src%2Fmain.ts
https://medium.com/ngconf/new-in-angular-updated-control-flow-b6f0d6af7dfe
https://github.com/eduardoRoth/v17-control-flow
<div class="add-new">
  @if (showAddName()) {
    <input type="text" [formControl]="newName" />
    <button (click)="addName()">Add name</button>
    <button (click)="showAddName.set(false)">Close</button>
  } @else {
    <button (click)="showAddName.set(true)">Add a new name</button>
  }
</div>

<ul class="names">
  @for (name of names(); track name) {
    <li>
      {{name}}
    </li>
  } @empty {
    <li>Name list is empty</li>
  }
</ul>



👌 Goodbye if-else, Hello Pattern Matching in JavaScript (PROPOSAL)
https://medium.com/@techsuneel99/goodbye-if-else-hello-pattern-matching-in-javascript-proposal-e8682458d863
https://codeeverywhere.medium.com/goodbye-if-else-hello-pattern-matching-in-javascript-52bd46eda41f


👌 private zone: NgZone
https://netbasal.com/optimizing-angular-change-detection-triggered-by-dom-events-d2a3b2e11d87
export class TestComponent {
  constructor(private zone: NgZone) {}

  ngOnInit() {
    this.zone.runOutsideAngular(() => {
      // don't forget to unsubscribe
      fromEvent(window, 'scroll').subscribe(...);
    });
}

👌 Feature Flags in Angular 16
https://levelup.gitconnected.com/feature-flags-in-angular-16-472254256b0c


👌 https://medium.com/@codelogy/garbage-collection-with-destroyref-in-angular-16-6497d8ed44b0
Garbage collection with DestroyRef in Angular 16

import { Component, DestroyRef, inject, OnInit } from '@angular/core';

@Component({
  selector: 'app-timeout-destroy-ref',
  template: ''
})
export class TimeoutDestroyRefComponent implements OnInit {
  private _destroyRef = inject(DestroyRef);

  ngOnInit() {
    // Run some action after 5 seconds
    const timeout = setTimeout(() => {
      console.log('Some action');
    }, 5000);
    // register a destroy callback
    this._destroyRef.onDestroy(() => {
      clearTimeout(timeout);
    });
  }
}

👌 PWA: Mastering Web Service Workers in Angular: A Comprehensive Guide
https://medium.com/@zeeshankhan8838/mastering-web-service-workers-in-angular-a-comprehensive-guide-8a6ebad4ac29
ng add @angular/pwa

👌 @Input() How I’ve Created Custom Inputs in Angular 16!
https://blog.bitsrc.io/how-ive-created-custom-inputs-in-angular-16-43f4c2d37d07

import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-component',
  template: `
  <h1>Input Decorator Features in Angular 16 Example</h1>

  <input type="text" [(ngModel)]="name" placeholder="Name" required />
  <input type="number" [(ngModel)]="age" placeholder="Age" />
  <input type="text" [(ngModel)]="customName" placeholder="Custom Name" />

  <p>Name: {{ name }}</p>
  <p>Age: {{ age }}</p>
  <p>Custom Name: {{ customName }}</p>
  `,
})
export class AppComponent {

  @Input({ required: true })
  name: string;

  @Input({ transform: (value: string) => parseInt(value, 10) })
  age: number;

  @Input({ alias: 'customName' })
  customName: string;

}

👌 debounceTime
https://netbasal.com/take-advantage-of-the-let-operator-in-angular-d351fd4bd1d9

@Component({
  selector: 'app-input',
  template: `
    <input type="text" [formControl]="form" class="form-control">
  `,
})
export class AppInput {
  @Output() value = new EventEmitter();
  @Input() middleware = valueChangesObservable => valueChangesObservable;
  form;
  
  ngOnInit() {
    this.form = new FormControl();
    
    this.form.valueChanges.let(this.middleware).subscribe(val => {
      this.value.next(val);
    });
  }
  
  ngOnDestory() {
    // unsubscribe
  }
  
}


@Component({
  selector: 'my-app',
  template: `
   <app-input (value)="doSomething($event)" [middleware]="middleware"></app-input>
  `,
})
export class App {
  middleware = valueChangesObservable => valueChangesObservable.debounceTime(1000);
  
  doSomething(val) {
    console.log(val);
  }
  
}

````

# animations
````
👌 Lots of animations
https://stackblitz.com/edit/angular-animation-directive-ad-pdpbym?file=README.md
````

# codepen
````
👌 17+ CSS Round Buttons
https://alvarotrigo.com/blog/css-round-button/

````




# To change the data between two different arrays, with position A receiving value B and position B receiving value A from twisted arrays

````
                               EX 1..........................
    const text = [];
    this.monthNames = []
    const newArray = [];

    for (let i = 0; i < text.length; i++) {
      const newObj = {
        a: this.monthNames[i].a,
        b: text[i].b
      };
      newArray.push(newObj);
    }

    console.log('wwwwww',newArray);


			 EX 2..........................RXJS

    let example: any; // const example = new Subject<any>();
    example = forkJoin({
      // emit 'Hello' immediately
      sourceOne: of(text),
      sourceTwo: of(this.monthNames).pipe(delay(1000)),
    }).pipe(
      map(res => {
	let array1 = res.sourceOne
	let array2 = res.sourceTwo

	const newArray = [];

	for (let i = 0; i < array1.length; i++) {
	  const newObj = {
	    a: array2[i].a,
	    b: array1[i].b
	  };
	  newArray.push(newObj);
	}

	return newArray
      }),
      catchError(error => of(error))
    )

    example
      .subscribe({
	next: (res: any) => {
	  console.log('RESULTADO', res)
	},
	error: () => { },
	complete: () => { }
      })


                             EX 3..........................RXJS concatAll() ... para outra situação

const obs1 = of(text);
const obs2 = of(this.monthNames);
// const source = of(obs1, obs2);
const source = of(text, this.monthNames);
const example = source.pipe(
concatAll()
);
example.subscribe((val:any) => {
console.log(val)
// let a = val.filter((b:any) => b == 0);
// console.log(a)
});

````

# ANIMAÇÃO ANGULAR

````
https://stackblitz.com/edit/angular-animations-lib-demo-ine1m8
https://github.com/filipows/angular-animations

````


# MICRO FRONTE END

#### 🌝 mplement micro frontends in Angular using Nx


````
https://onna.dev/implement-micro-frontends-in-angular-using-nx/
https://github.com/Gabriel10Velloso/Micro-fronte-using-Nx
https://github.com/ebrehault/micro-frontend-with-nx
https://github.com/Gabriel10Velloso/multiple-angular-applications
https://github.com/Gabriel10Velloso/micro-angular-elements-
````



# Angular ElementRef Renderer2 @Inject(DOCUMENT)

#### 🌝 getElementById
#### this.renderer.appendChild(this.elementRef.nativeElement, link);
#### this.renderer2.setProperty(this.elementRef.nativeElement, 'href', 'https://github.com/Gabriel10Velloso');
#### this.renderer2.setAttribute(this.elementRef.nativeElement, 'target', '_blank');

````
https://stackblitz.com/edit/importante-viewchild-addclass
````


# Angular-casos-estudo

#### 🌝 Angular inDepth.dev
#### https://indepth.dev/angular
````
https://indepth.dev/angular
````

````
------------------------------------ // ---------------------------------------------------------
````

#### 🍦 lazy-loaded Angular modules for Ivy!

````
    RouterModule.forRoot([
      { 
        path: 'lazy',
        loadChildren: async () => {
          const { LazyModule } = await import('./lazy/lazy.module');
          return LazyModule;
        }
      }
    ]),
````


````
------------------------------------ // ---------------------------------------------------------
````


#### 🌄 Autofocus That Works Anytime in Angular Apps
###### https://netbasal.com/autofocus-that-works-anytime-in-angular-apps-68cb89a3f057

````
<input autofocus>
````


````
------------------------------------ // ---------------------------------------------------------
````

#### 🎃 Integrate Stripe with Angular 10
###### https://medium.com/bitontree/integrate-stripe-with-angular-10-e9e86874d889

````
O Stripe fornece várias bibliotecas JavaScript - Stripe Elements & Checkout - que tornam conveniente coletar e validar fontes de pagamento como cartões de crédito, contas bancárias e muito mais. Com Stripe.js, você também pode tokenizar informações confidenciais, integrar com Checkout e lidar com autenticação 3D Secure.

````


````
------------------------------------ // ---------------------------------------------------------
````

#### 👆 Creatively Decouple ngOnChanges
###### https://medium.com/angular-in-depth/creatively-decouple-ngonchanges-fab95395cc6e
###### https://stackblitz.com/edit/ngonchanges-simplechanges?file=app%2Fapp.component.ts
###### https://stackblitz.com/edit/ngonchanges-example-1?file=src%2Fapp%2Fdoctor-card%2Fdoctor-card.component.ts
###### https://stackblitz.com/edit/angular-ivy-sbyzya?file=src%2Fapp%2Fdata-table-onchange.component.ts

````
When it comes to subscribing to property changes in Angular, I think most people would immediately think of thengOnChanges lifecycle hook. A typical example looks like this:

````

````
------------------------------------ // ---------------------------------------------------------
````


#### 🧯 Dynamic Components in Angular (IMPORTANTE)
###### https://codeburst.io/dynamic-components-in-angular-8fd12490ab8
###### https://github.com/Gabriel10Velloso/pet-chat-ComponentFactoryResolver


````
  ngOnInit(): void {
    this.viewContainerRef.clear();
    const cat = this.member as Cat;
    const dog = this.member as Dog;
    if (cat.favoriteComfyPlace) {
      const catComponentFactory = this.componentFactoryResolver.resolveComponentFactory(CatItemComponent);
      const componentRef = this.viewContainerRef.createComponent(catComponentFactory);
      componentRef.instance.member = cat;
    } else if (dog.favoritePark) {
      const dogComponentFactory = this.componentFactoryResolver.resolveComponentFactory(DogItemComponent);
      const componentRef = this.viewContainerRef.createComponent(dogComponentFactory);
      componentRef.instance.member = dog;
    }
  }

````

````
------------------------------------ // ---------------------------------------------------------
````


#### ❤️ Angular — Using NgTemplateOutlet to communicate between parent and dynamic child components
###### https://stackblitz.com/edit/ng-template-outlet-simple-inwkbw?file=src%2Fapp%2Fdetail-projection%2Fdetail-projection.component.html
###### 


````
<div class="outer">
	Outer Bix
	<ng-template [ngTemplateOutlet]="detail" *ngIf="outside"></ng-template>
	<div class="inner">
		inner box
		<ng-template [ngTemplateOutlet]="detail" *ngIf="!outside"></ng-template>
	</div>
</div>

````

````
------------------------------------ // ---------------------------------------------------------
````


####  🏹 Usando Angular CDK Portal para criar um Modal
###### https://stackblitz.com/edit/angular-cdk-portals-czpd1p -- HEADER EXEMPLO
###### https://medium.com/@joaoghignatti/usando-angular-cdk-portal-para-criar-um-modal-213f5551ec1
###### https://stackblitz.com/github/JGhignatti/angular-cdk-modal?file=src%2Fapp%2Fmodal%2Fservices%2Fgeneric-modal.service.ts
###### https://github.com/Gabriel10Velloso/angularsp-cdk-portal
###### https://stackblitz.com/edit/portals-demo?file=app%2Fapp.component.ts


````
<div bsModal
     #modal="bs-modal"
     class="modal fade"
     tabindex="-1"
     role="dialog"
     [config]="{ignoreBackdropClick: true, keyboard: false}"
     [class.right]="position === modalPositionEnum.RIGHT">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">

      <div class="modal-body">
        <ng-container *cdkPortalOutlet></ng-container>
      </div>

    </div>
  </div>
</div>

````

````
------------------------------------ // ---------------------------------------------------------
````

####  🅰️ Angular Elements
###### https://stackblitz.com/edit/angular-elements-demo-if3dxp
###### https://stackblitz.com/edit/angular-qcwuw7?file=src/app/popup.service.ts
###### https://www.youtube.com/watch?v=y73NMviRoPY
###### https://stackblitz.com/edit/angular-elements-ivy-ehw51p?file=src%2Findex.html


````
  constructor(injector: Injector, public popup: PopupService) {
    // Convert `PopupComponent` to a custom element.
    const PopupElement = createCustomElement(PopupComponent, {injector});
    // Register the custom element with the browser.
    customElements.define('popup-element', PopupElement);
  }
  
  
  
  <html>
  <head>
    <title>Angular App</title>
    <script>
      function loadElement() {
        const container = document.querySelector('#container');
        const elm = document.createElement('app-element');
        const items = [
          'Item 1',
          'Item 2',
          'Item 3',
        ];
        elm.label = "My List";
        elm.items = items;
        container.appendChild(elm);
      }      
    </script>
  </head>
  <body>
    <button onclick="loadElement()">Load Element</button>
    <div id="container">
      <!-- element loads here -->
    </div>
  </body>
</html>
````

````
------------------------------------ // ---------------------------------------------------------
````


####  🔇 Angular Resolver for Prefetching Data
###### https://javascript.plainenglish.io/angular-resolver-for-prefetching-data-angular-guards-resolve-40fda257d666
###### https://stackblitz.com/edit/angular-route-resolvers-brbkr6
````
import { Injectable } from '@angular/core';
import { Resolve } from '@angular/router';
import { Observable, of } from 'rxjs';

import { GithubUserService } from './github-user.service';

@Injectable()
export class UserResolver implements Resolve<Observable<any>> {
  constructor(private userService: GithubUserService) {}

  resolve(): Observable<any> {
    return this.userService.getUsers();
  }
}
````

````
------------------------------------ // ---------------------------------------------------------
````










