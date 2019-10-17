---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319189"
---
# <a name="where-entity-sql"></a>WHERE (Entity SQL)
La clausola WHERE viene applicata direttamente dopo la clausola [from](from-entity-sql.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Tipo Boolean.  
  
## <a name="remarks"></a>Note  
 La clausola WHERE ha la stessa semantica descritta per Transact-SQL. Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.  
  
```sql  
select c from cs as c where e  
```  
  
 L'espressione `e` deve essere di tipo Boolean.  
  
 La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione. Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Espressioni di query](query-expressions-entity-sql.md)
