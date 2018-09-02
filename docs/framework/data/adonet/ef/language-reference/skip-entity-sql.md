---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 321f6c5ae62ce21249ae4c1081b8e98427bc3df2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425738"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)
Il paging fisico può essere eseguito usando la sottoclausola SKIP nella clausola ORDER BY. Non è possibile usare SKIP separatamente dalla clausola ORDER BY.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `n`  
 Numero di elementi da ignorare.  
  
## <a name="remarks"></a>Note  
 Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP. SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti.  
  
> [!NOTE]
>  Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP. È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.  
  
> [!NOTE]
>  In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti. Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato. Questo comportamento è dovuto alla modalità di conversione di SKIP per [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 Nella query  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in [questo](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) esempio viene usato l'operatore ORDER BY con SKIP per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.  
  
## <a name="see-also"></a>Vedere anche  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Procedura: spostarsi tra Query i risultati](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
