---
title: Funzioni spaziali
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797696"
---
# <a name="spatial-functions"></a>Funzioni spaziali
Nessun formato letterale per i tipi spaziali. Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text. Ad esempio, la seguente chiamata di funzione crea un punto di geometria:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Il <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> metodi hanno tutti i metodi canonici spaziali di Entity Framework. Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.
