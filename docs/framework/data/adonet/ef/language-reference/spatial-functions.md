---
title: Funzioni spaziali
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7b78cbf4dc53ba1bc4148fa0077615e43cc8f9f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763930"
---
# <a name="spatial-functions"></a>Funzioni spaziali
Nessun formato letterale per i tipi spaziali. Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text. Ad esempio, la seguente chiamata di funzione crea un punto di geometria:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Il [metodi SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) pagina vengono elencati tutti i metodi canonici spaziali di Entity Framework. Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.
