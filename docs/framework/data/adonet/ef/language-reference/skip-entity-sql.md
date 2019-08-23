---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 6ddbdd41a00b3934649b24ca96a5a07e5cbf0d34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911143"
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
> Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP. È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.  
  
> [!NOTE]
> In SQL Server 2000, l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti. Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato. Ciò è dovuto alla modalità di conversione di SKIP per SQL Server 2000. Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [procedura: La pagina tramite i](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) risultati della query usa l'operatore ORDER BY con Skip per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.  
  
## <a name="see-also"></a>Vedere anche

- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Procedura: Pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
