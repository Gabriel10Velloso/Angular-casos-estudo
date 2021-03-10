# Angular-casos-estudo

#### lazy-loaded Angular modules for Ivy!

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
