---
title: Precedenza tra gli operatori (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159133"
---
# <a name="operator-precedence-entity-sql"></a>Precedenza tra gli operatori (Entity SQL)
Quando un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query include più operatori, precedenza degli operatori determina la sequenza in cui le operazioni vengono eseguite. L'ordine di esecuzione può modificare in modo significativo il risultato della query.  
  
 Nella tabella seguente sono indicati i livelli di precedenza degli operatori. Un operatore con livello di precedenza più alto viene valutato prima di un operatore con livello di precedenza più basso.  
  
|Livello|Tipo di operazione|Operatore|  
|-----------|--------------------|--------------|  
|1|Primario|`. , [] ()`|  
|2|Unario|`! not`|  
|3|Moltiplicazione|`* / %`|  
|4|Addizione|`+ -`|  
|5|Ordering|`< > <= >=`|  
|6|Uguaglianza|`= != <>`|  
|7|AND condizionale|`and &&`|  
|8|OR condizionale|`or &#124;&#124;`|  
  
 Se due operatori in un'espressione hanno lo stesso livello di precedenza, vengono valutati da sinistra verso destra in base alla posizione nella query. L'espressione `x+y-z` viene ad esempio valutata come `(x+y)-z`.  
  
 Per ignorare l'ordine di precedenza predefinito degli operatori in una query, è possibile usare le parentesi. Tutti gli operatori racchiusi tra parentesi vengono valutati per primi in modo da ottenere un singolo risultato, che verrà quindi usato dagli operatori all'esterno delle parentesi. Ad esempio, `x+y*z` Moltiplica `y` dal `z` e quindi aggiunge `x`, ma `(x+y)*z` aggiunge `x` al `y` e quindi moltiplica il risultato per `z`.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
