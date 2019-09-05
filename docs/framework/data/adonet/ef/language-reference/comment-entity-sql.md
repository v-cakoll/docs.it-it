---
title: -- (commento) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 1ea1929b0e6f965f71fbb015ee6795affb3bce7c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251212"
---
# <a name="---comment-entity-sql"></a>-- (commento) (Entity SQL)
Le query[!INCLUDE[esql](../../../../../../includes/esql-md.md)] possono contenere commenti. Due trattini (`--`) indicano l'inizio di una riga di commento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Argomenti  
 `text_of_comment`  
 Stringa di caratteri contenente il testo del commento.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene illustrato come usare i commenti. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](entity-sql-overview.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
