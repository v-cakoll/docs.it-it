---
title: SKIP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 75140384823588b8f6785de00b0ab3cd17314a3f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319334"
---
# <a name="skip-entity-sql"></a>SKIP (Entity SQL)

Il paging fisico può essere eseguito usando la sottoclausola SKIP nella clausola ORDER BY. Non è possibile usare SKIP separatamente dalla clausola ORDER BY.

## <a name="syntax"></a>Sintassi

```sql
[ SKIP n ]
```

## <a name="arguments"></a>argomenti

`n` \
Numero di elementi da ignorare.

## <a name="remarks"></a>Note

Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP. SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti.

> [!NOTE]
> Una query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene considerata non valida se nella stessa espressione di query sono presenti sia il modificatore TOP che la sottoclausola SKIP. È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.

> [!NOTE]
> In SQL Server 2000, l'uso di SKIP con ORDER BY in colonne non chiave può restituire risultati non corretti. Se la colonna non chiave include dati duplicati, potrebbe venire ignorato un numero di righe maggiore di quello specificato. Ciò è dovuto alla modalità di conversione di SKIP per SQL Server 2000. Nel codice seguente potrebbero ad esempio venire ignorate più di cinque righe se `E.NonKeyColumn` include valori duplicati:
>
> ```sql
> SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L
> ```

La query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in [procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100)) utilizza l'operatore ORDER BY con Skip per specificare l'ordinamento utilizzato per gli oggetti restituiti in un'istruzione SELECT.

## <a name="see-also"></a>Vedere anche

- [ORDER BY](order-by-entity-sql.md)
- [Procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Paging](paging-entity-sql.md)
- [TOP](top-entity-sql.md)
