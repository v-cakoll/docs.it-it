---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 4055d56d878b817fe88bb0dacb53ea39061bc4b2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249854"
---
# <a name="-not-entity-sql"></a>! (NOT) (Entity SQL)
Nega un'espressione `Boolean` .  
  
## <a name="syntax"></a>Sintassi  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `boolean_expression`  
 Qualsiasi espressione valida che restituisce un valore Boolean.  
  
## <a name="remarks"></a>Note  
 Il punto esclamativo (!) ha la stessa funzionalità dell'operatore NOT.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore NOT per negare un'espressione `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
