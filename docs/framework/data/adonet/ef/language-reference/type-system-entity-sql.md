---
title: Sistema di tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: f99d63bd526981c4a9f079c25851dc9bbd89cf7c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738470"
---
# <a name="type-system-entity-sql"></a>Sistema di tipi (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta diversi tipi:  
  
- Tipi primitivi (semplici), come `Int32` e `String.`.  
  
- Tipi nominali definiti nello schema, ad esempio <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> e <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
- Tipi anonimi non definiti esplicitamente nello schema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> e <xref:System.Data.Metadata.Edm.RefType>.  
  
 In questa sezione vengono illustrati i tipi anonimi che non sono definiti in modo esplicito nello schema, ma sono supportati da Entity SQL. Per informazioni sui tipi primitivi e nominali, vedere [tipi di modelli concettuali (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).  
  
## <a name="rows"></a>Righe  
 La struttura di una riga dipende dalla sequenza di membri tipizzati e denominati di cui è composta la riga stessa. Un tipo di riga non dispone dell'identità e non può essere ereditato. Le istanze dello stesso tipo di riga sono equivalenti se i membri sono rispettivamente equivalenti. Le righe non hanno alcun comportamento al di là dell'equivalenza strutturale e non dispongono di equivalenti in Common Language Runtime. Le query possono produrre strutture contenenti righe o raccolte di righe. L'associazione API tra le query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e il linguaggio host definisce la realizzazione delle righe nella query che ha prodotto il risultato. Per informazioni su come creare un'istanza di riga, vedere [costruzione di tipi](constructing-types-entity-sql.md).  
  
## <a name="collections"></a>Raccolte  
 I tipi di raccolta rappresentano zero o più istanze di altri oggetti. Per informazioni su come costruire la raccolta, vedere [costruzione di tipi](constructing-types-entity-sql.md).  
  
## <a name="references"></a>Riferimenti  
 Un riferimento è un puntatore logico a un'entità specifica in un set di entità specifico.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta gli operatori seguenti per costruire o annullare i riferimenti, nonché eseguire la navigazione al loro interno:  
  
- [REF](ref-entity-sql.md)  
  
- [CREATEREF](createref-entity-sql.md)  
  
- [KEY](key-entity-sql.md)  
  
- [DEREF](deref-entity-sql.md)  
  
 È possibile navigare da un riferimento all'altro tramite l'operatore (punto) di accesso ai membri (`.`). Nel frammento seguente viene estratta la proprietà Id (di Order) spostandosi nella proprietà r (riferimento).  
  
```sql  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 Se il valore di riferimento è null o la destinazione del riferimento non esiste, il risultato è null.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](entity-sql-overview.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
- [CAST](cast-entity-sql.md)
- [Specifiche CSDL, SSDL e MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
