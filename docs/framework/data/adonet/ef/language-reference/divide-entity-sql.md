---
title: '- Dividere (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: d4e4c1449b665e6dea22bfcc0ee2277478b4da1a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251059"
---
# <a name="-divide-entity-sql"></a>/ (divisione) (Entity SQL)
Divide un numero per un altro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a>Argomenti  
 `dividend`  
 Espressione numerica da dividere. `dividend` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.  
  
 `divisor`  
 Espressione numerica per la quale dividere il dividendo. `divisor` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.  
  
## <a name="result-types"></a>Tipi di risultati  
 Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti. Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore aritmetico/per dividere un numero per un altro. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
