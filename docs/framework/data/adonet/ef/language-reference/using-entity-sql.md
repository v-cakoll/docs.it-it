---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 9495e5daf88326c5a682172d835c3349fe79e571
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248754"
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
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Vedere anche

- [Spazi dei nomi](namespaces-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
