---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 0e611add4ce3f20e42bb01b0bf0392bbe81ec548
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251191"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
La parola chiave COLLECTION viene usata solo nella definizione di una funzione inline. Le funzioni di raccolta sono funzioni che operano su una raccolta di valori e producono un output scalare.  
  
## <a name="syntax"></a>Sintassi  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>Argomenti  
 `type_definition`  
 Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sulla parola chiave COLLECTION, vedere [Type Definitions](type-definitions-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come usare la parola chiave COLLECTION per dichiarare una raccolta di numeri decimali come argomento di una funzione inline della query.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
