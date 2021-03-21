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






