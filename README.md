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


````
  constructor(injector: Injector, public popup: PopupService) {
    // Convert `PopupComponent` to a custom element.
    const PopupElement = createCustomElement(PopupComponent, {injector});
    // Register the custom element with the browser.
    customElements.define('popup-element', PopupElement);
  }
````

````
------------------------------------ // ---------------------------------------------------------
````









