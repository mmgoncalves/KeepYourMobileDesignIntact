# KeepYourMobileDesignIntact
Apenas uma pequena dica de como manter o design da sua aplicação intacto independente da escolha de tamanho de fonte feita pelo usuário nas configurações do celular

##A solução se resume em 2 passos simples:##

* 1: Instale o plugin do cordova para acessibilidade
```javascript
    $ cordova plugin add https://github.com/phonegap/phonegap-mobile-accessibility.git
```

* 2: Aplicar a solução no seu projeto IONIC

No seu arquivo app.js 

```javascript
  .run(function ($ionicPlatform, $window) {
      $ionicPlatform.ready(function () {
          //Evita que a configuração de tamanho de fonte do celular incluencie no app
          if ($window.MobileAccessibility) {
              $window.MobileAccessibility.usePreferredTextZoom(false);
          }
      });
  });
```
