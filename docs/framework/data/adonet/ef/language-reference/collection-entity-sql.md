---
title: COLLECTION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c850fe215c692f204c6762d82a3d37b29c556a7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
