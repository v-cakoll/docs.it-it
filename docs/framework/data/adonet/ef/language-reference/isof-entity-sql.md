---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 87d69f58fc0c45eacb4ee63997129347f7f2a857
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827409"
---
# <a name="isof-entity-sql"></a>ISOF (Entity SQL)
Determina se il tipo di un'espressione è del tipo specificato o di uno dei sottotipi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>Argomenti  
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
 Le espressioni `expression IS NOT OF (type)` e `expression IS NOT OF (ONLY type)` sono sintatticamente equivalenti a `NOT (expression IS OF (type))` e `NOT (expression IS OF (ONLY type))`, rispettivamente.  
  
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
 Nell'esempio [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query Usa l'operatore IS OF per determinare il tipo di un'espressione di query e quindi Usa l'operatore TREAT per convertire un oggetto del tipo Course in una raccolta di oggetti del tipo OnsiteCourse. La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>Vedere anche
- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
