---
title: Parametri (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187674"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="46f6e-102">Parametri (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="46f6e-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="46f6e-103">I parametri sono variabili definite esternamente a [!INCLUDE[esql](../../../../../../includes/esql-md.md)], generalmente tramite un'API di associazione usata da un linguaggio host.</span><span class="sxs-lookup"><span data-stu-id="46f6e-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="46f6e-104">Ogni parametro è associato a un nome e un tipo.</span><span class="sxs-lookup"><span data-stu-id="46f6e-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="46f6e-105">I nomi dei parametri sono definiti nelle espressioni di query con il simbolo chiocciola (@) come prefisso.</span><span class="sxs-lookup"><span data-stu-id="46f6e-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="46f6e-106">Questo consente di distinguerli dai nomi di proprietà o dagli altri nomi definiti nella query.</span><span class="sxs-lookup"><span data-stu-id="46f6e-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="46f6e-107">L'API di associazione del linguaggio host fornisce le API per l'associazione dei parametri.</span><span class="sxs-lookup"><span data-stu-id="46f6e-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46f6e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="46f6e-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="46f6e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46f6e-109">See also</span></span>

- [<span data-ttu-id="46f6e-110">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="46f6e-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="46f6e-111">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="46f6e-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
