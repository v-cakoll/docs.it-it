---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039899"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
La parola chiave COLLECTION viene usata solo nella definizione di una funzione inline. Le funzioni di raccolta sono funzioni che operano su una raccolta di valori e producono un output scalare.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a>argomenti  
 `type_definition`  
 Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sulla parola chiave COLLECTION, vedere [Type Definitions](type-definitions-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come usare la parola chiave COLLECTION per dichiarare una raccolta di numeri decimali come argomento di una funzione inline della query.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
