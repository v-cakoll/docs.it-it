---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 9d35306d1299e91ecaa55a7d2818ee1e2982793f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249202"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Restituisce un riferimento a un'istanza dell'entità.  
  
## <a name="syntax"></a>Sintassi  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida che produce un'istanza di un tipo di entità.  
  
## <a name="return-value"></a>Valore restituito  
 Riferimento all'istanza dell'entità specificata.  
  
## <a name="remarks"></a>Note  
 Un riferimento all'entità è costituito dalla chiave di entità e dal nome di un set di entità. Poiché set di entità diversi possono essere basati sullo stesso tipo di entità, una determinata chiave di entità può essere visualizzata in più set di entità. Un riferimento all'entità è tuttavia sempre univoco. Se l'espressione di input rappresenta un'entità persistente, verrà restituito un riferimento a tale entità. Se l'espressione di input non è un'entità persistente, verrà restituito un riferimento Null.  
  
 Quando viene usato l'operatore di estrazione delle proprietà (.), il riferimento viene automaticamente dereferenziato.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore REF per restituire il riferimento per un argomento dell'entità di input. Nella stessa query il riferimento viene dereferenziato in quanto viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà dell'entità Product. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>Vedere anche

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Definizioni di tipo](type-definitions-entity-sql.md)
