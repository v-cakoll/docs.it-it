---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 02eeaeb8cfa335e5545b26d3d52b91c4e1614629
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230707"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
La clausola WHERE viene applicata direttamente dopo il [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clausola.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Tipo Boolean.  
  
## <a name="remarks"></a>Note  
 La clausola WHERE dispone della stessa semantica descritta per [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.  
  
```  
select c from cs as c where e  
```  
  
 L'espressione `e` deve essere di tipo Boolean.  
  
 La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione. Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Espressioni di query](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
