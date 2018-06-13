---
title: -- (commento) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764164"
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
  
1.  Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
