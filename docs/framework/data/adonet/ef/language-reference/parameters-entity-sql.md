---
title: Parametri (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 8fbca4f10a7c2c3dbaffff978a536b87d31a8df4
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319425"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="71097-102">Parametri (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="71097-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="71097-103">I parametri sono variabili definite esternamente a [!INCLUDE[esql](../../../../../../includes/esql-md.md)], generalmente tramite un'API di associazione usata da un linguaggio host.</span><span class="sxs-lookup"><span data-stu-id="71097-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="71097-104">Ogni parametro è associato a un nome e un tipo.</span><span class="sxs-lookup"><span data-stu-id="71097-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="71097-105">I nomi dei parametri sono definiti nelle espressioni di query con il simbolo chiocciola (@) come prefisso.</span><span class="sxs-lookup"><span data-stu-id="71097-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="71097-106">Questo consente di distinguerli dai nomi di proprietà o dagli altri nomi definiti nella query.</span><span class="sxs-lookup"><span data-stu-id="71097-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="71097-107">L'API di associazione del linguaggio host fornisce le API per l'associazione dei parametri.</span><span class="sxs-lookup"><span data-stu-id="71097-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71097-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="71097-108">Example</span></span>  
  
```sql  
SELECT c   
      FROM LOB.Customers AS c   
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="71097-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71097-109">See also</span></span>

- [<span data-ttu-id="71097-110">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="71097-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="71097-111">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="71097-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
