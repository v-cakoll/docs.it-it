---
title: Parametri (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187674"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="0ee1f-102">Parametri (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0ee1f-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="0ee1f-103">I parametri sono variabili definite esternamente a [!INCLUDE[esql](../../../../../../includes/esql-md.md)], generalmente tramite un'API di associazione usata da un linguaggio host.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="0ee1f-104">Ogni parametro è associato a un nome e un tipo.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="0ee1f-105">I nomi dei parametri sono definiti nelle espressioni di query con il simbolo chiocciola (@) come prefisso.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="0ee1f-106">Questo consente di distinguerli dai nomi di proprietà o dagli altri nomi definiti nella query.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="0ee1f-107">L'API di associazione del linguaggio host fornisce le API per l'associazione dei parametri.</span><span class="sxs-lookup"><span data-stu-id="0ee1f-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee1f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ee1f-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ee1f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee1f-109">See also</span></span>

- [<span data-ttu-id="0ee1f-110">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0ee1f-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0ee1f-111">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0ee1f-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
