---
title: Funzioni spaziali
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319297"
---
# <a name="spatial-functions"></a>Funzioni spaziali
Nessun formato letterale per i tipi spaziali. Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text. Ad esempio, la seguente chiamata di funzione crea un punto di geometria:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 I metodi <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> hanno tutti i metodi di Entity Framework canonici spaziali. Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.
