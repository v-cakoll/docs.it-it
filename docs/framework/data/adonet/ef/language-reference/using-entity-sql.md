---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297863"
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Specifica gli spazi dei nomi usati in un'espressione di query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argomenti  
 `alias`  
 Specifica un alias più breve con cui qualificare uno spazio dei nomi.  
  
 `namespace`  
 Qualsiasi spazio dei nomi valido.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Vedere anche

- [Spazi dei nomi](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
