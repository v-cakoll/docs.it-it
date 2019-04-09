---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 8cd440571726796ee3d2c91e0d2f6b50571e8e27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217757"
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
 Per altre informazioni sulla parola chiave COLLECTION, vedere [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come usare la parola chiave COLLECTION per dichiarare una raccolta di numeri decimali come argomento di una funzione inline della query.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
