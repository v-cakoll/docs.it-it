---
title: Funzioni spaziali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c482c2f79c6416a4e748599c896280b426d31ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="spatial-functions"></a>Funzioni spaziali
Nessun formato letterale per i tipi spaziali. Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text. Ad esempio, la seguente chiamata di funzione crea un punto di geometria:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Il [metodi SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) pagina vengono elencati tutti i metodi canonici spaziali di Entity Framework. Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.
