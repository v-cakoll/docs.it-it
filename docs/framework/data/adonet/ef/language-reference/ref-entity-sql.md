---
title: REF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 08bcaad4fdc0cf5324ff9976fcf48c23b206e72f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319387"
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
Restituisce un riferimento a un'istanza dell'entità.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
REF( expression )   
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione valida che produce un'istanza di un tipo di entità.  
  
## <a name="return-value"></a>Valore restituito  
 Riferimento all'istanza dell'entità specificata.  
  
## <a name="remarks"></a>Note  
 Un riferimento all'entità è costituito dalla chiave di entità e dal nome di un set di entità. Poiché set di entità diversi possono essere basati sullo stesso tipo di entità, una determinata chiave di entità può essere visualizzata in più set di entità. Un riferimento all'entità è tuttavia sempre univoco. Se l'espressione di input rappresenta un'entità persistente, verrà restituito un riferimento a tale entità. Se l'espressione di input non è un'entità persistente, verrà restituito un riferimento Null.  
  
 Quando viene usato l'operatore di estrazione delle proprietà (.), il riferimento viene automaticamente dereferenziato.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore REF per restituire il riferimento per un argomento dell'entità di input. Nella stessa query il riferimento viene dereferenziato in quanto viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà dell'entità Product. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>Vedere anche

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Definizioni di tipo](type-definitions-entity-sql.md)
