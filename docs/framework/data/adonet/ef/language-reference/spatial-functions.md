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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: acc09f9ea83e42377d0ba633927ecef13d5f46a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="spatial-functions"></a>Funzioni spaziali
Nessun formato letterale per i tipi spaziali. Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text. Ad esempio, la seguente chiamata di funzione crea un punto di geometria:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Il [metodi SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) pagina vengono elencati tutti i metodi canonici spaziali di Entity Framework. Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.
