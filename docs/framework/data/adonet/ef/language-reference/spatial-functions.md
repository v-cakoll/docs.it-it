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
# <a name="spatial-functions"></a><span data-ttu-id="e48e8-102">Funzioni spaziali</span><span class="sxs-lookup"><span data-stu-id="e48e8-102">Spatial Functions</span></span>
<span data-ttu-id="e48e8-103">Nessun formato letterale per i tipi spaziali.</span><span class="sxs-lookup"><span data-stu-id="e48e8-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="e48e8-104">Tuttavia, è possibile usare le funzioni canoniche di Entity Framework che si chiamano tramite stringhe in formato Well-Known Text.</span><span class="sxs-lookup"><span data-stu-id="e48e8-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="e48e8-105">Ad esempio, la seguente chiamata di funzione crea un punto di geometria:</span><span class="sxs-lookup"><span data-stu-id="e48e8-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="e48e8-106">Il <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> metodi hanno tutti i metodi canonici spaziali di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e48e8-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="e48e8-107">Fare clic su un metodo per visualizzare i parametri che devono essere passati a una funzione.</span><span class="sxs-lookup"><span data-stu-id="e48e8-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
