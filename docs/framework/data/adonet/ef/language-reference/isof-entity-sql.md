---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: c4c4cbf74cb17cf43e79c42ff42d1e68122fd534
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319710"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Determina se il tipo di un'espressione è del tipo specificato o di uno dei sottotipi.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione di query valida di cui determinare il tipo.  
  
 NOT  
 Nega il risultato EDM.Boolean di IS OF.  
  
 ONLY  
 Specifica che IS OF restituisce `true` solo se `expression` è di tipo `type` e non di uno dei sottotipi.  
  
 `type`  
 Tipo rispetto al quale testare `expression`. Il tipo deve essere qualificato dallo spazio dei nomi.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se `expression` è di tipo T e T è un tipo di base o un tipo derivato di `type`; null se `expression` è null in fase di runtime; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Le espressioni `expression IS NOT OF (type)` e `expression IS NOT OF (ONLY type)` sono sintatticamente equivalenti rispettivamente a `NOT (expression IS OF (type))` e `NOT (expression IS OF (ONLY type))`.  
  
 Nella tabella seguente viene illustrato il comportamento dell'operatore `IS OF` su alcuni modelli tipici e specifici. Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:  
  
|Criterio|Comportamento|  
|-------------|--------------|  
|null IS OF (EntityType)|Genera un'eccezione|  
|null IS OF (ComplexType)|Genera un'eccezione|  
|null IS OF (RowType)|Genera un'eccezione|  
|TREAT (null AS EntityType) IS OF (EntityType)|Restituisce DBNull|  
|TREAT (null AS ComplexType) IS OF (ComplexType)|Genera un'eccezione|  
|TREAT (null AS RowType) IS OF (RowType)|Genera un'eccezione|  
|EntityType IS OF (EntityType)|Restituisce true/false|  
|ComplexType IS OF (ComplexType)|Genera un'eccezione|  
|RowType IS OF (RowType)|Genera un'eccezione|  
  
## <a name="example"></a>Esempio  
 Nella query di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore IS OF per determinare il tipo di un'espressione di query, quindi viene usato l'operatore TREAT per convertire un oggetto del tipo Course in una raccolta di oggetti di tipo OnsiteCourse. La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [! code-SQL [DP EntityServices Concepts # TREAT_ISOF] ~/samples/snippets/tsql/VS_Snippets_Data/dp EntityServices Concepts/TSQL/EntitySql. SQL # TREAT_ISOF)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
