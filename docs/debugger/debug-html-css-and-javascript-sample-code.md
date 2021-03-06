---
title: Exemple de code HTML et CSS de déboguer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 51893967-98c8-4141-ba40-03646f221760
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2636e2a3a6fe3e99213198eb3296a765a664b4f4
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: fr-FR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227091"
---
# <a name="debug-html-and-css-sample-code"></a>Déboguer des exemples de code HTML et CSS

Le code dans cette rubrique est l’exemple de fichier pour [Guide de démarrage rapide : déboguer du code HTML et CSS](../debugger/quickstart-debug-html-and-css.md). Les erreurs présentes par conception dans le guide de démarrage rapide sont résolues dans cette version du code.

## <a name="sample-code"></a>Exemple de code
Le code HTML suivant est utilisé dans l’étiquette \<body> du guide de démarrage rapide.

```html
<div id="flipTemplate" data-win-control="WinJS.Binding.Template"
         style="display:none">
    <div class="fixedItem" >
        <img src="#" data-win-bind="src: flipImg" />
    </div>
</div>
<div id="fView" data-win-control="WinJS.UI.FlipView" data-win-options="{
    itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">
</div>
```

Le code CSS suivant montre les ajouts effectués à default.css.

```css
#fView {
    background-color:#0094ff;
    height: 500px;
    margin: 25px;
}
```

L'exemple de code suivant affiche le code JavaScript complet dans default.js. Les références aux espaces de noms WinJS pour ce code se trouvent dans le fichier default.html du modèle.

```javascript
(function () {
    "use strict";

    var app = WinJS.Application;
    var activation = Windows.ApplicationModel.Activation;

    var myData = [];
    for (var x = 0; x < 3; x++) {
        myData[x] = { flipImg: "/images/logo.png" }
    };

    var pages = new WinJS.Binding.List(myData, { proxy: true });

    app.onactivated = function (args) {
        if (args.detail.kind === activation.ActivationKind.launch) {
            if (args.detail.previousExecutionState !==
            activation.ApplicationExecutionState.terminated) {
                // TODO: . . .
            } else {
                // TODO: . . .
            }
            args.setPromise(WinJS.UI.processAll());

            updateImages();
        }
    };

    function updateImages() {

        pages.setAt(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });
        pages.setAt(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });
        pages.setAt(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });
    };

    app.oncheckpoint = function (args) {
    };

    app.start();

    var publicMembers = {
        items: pages
    };

    WinJS.Namespace.define("Data", publicMembers);

})();
```

## <a name="see-also"></a>Voir aussi
[Démarrage rapide : déboguer du code HTML et CSS](../debugger/quickstart-debug-html-and-css.md)
