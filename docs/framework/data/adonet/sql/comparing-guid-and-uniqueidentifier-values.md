---
title: Confronto tra GUID e valori uniqueidentifier
description: Informazioni su come creare e confrontare valori GUID nella .NET Framework provider di dati per SQL Server, rappresentati dal tipo di dati uniqueidentifier.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: 245b7246712822043d302c43a765c29ac2090e00
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286507"
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Confronto tra GUID e valori uniqueidentifier
Il tipo di dati identificatore univoco globale (GUID, Globally Unique IDentifier) in SQL Server è rappresentato dal tipo di dati `uniqueidentifier`, in cui è archiviato un valore binario di 16 byte. Un GUID è un numero binario usato principalmente come identificatore univoco in una rete con molti computer in più siti. I GUID possono essere generati chiamando la funzione NEWID di Transact-SQL. Si assicura l'univocità in tutto il mondo. Per altre informazioni, vedere [uniqueidentifier (Transact-SQL)](/sql/t-sql/data-types/uniqueidentifier-transact-sql).  
  
## <a name="working-with-sqlguid-values"></a>Uso di valori SqlGuid  
 I GUID sono valori lunghi e poco chiari, pertanto molti utenti non ne comprendono il significato. Se si usano GUID generati in modo casuale per valori chiave e se si inserisce un numero elevato di righe, l'I/O negli indici sarà casuale, determinando un impatto negativo sulle prestazioni. Rispetto ad altri tipo di dati, i GUID sono anche valori relativamente grandi. È in genere consigliabile usare i GUID solo per pochi scenari, nei quali non sono adatti altri tipi di dati.  
  
### <a name="comparing-guid-values"></a>Confronto di valori GUID  
 Con valori `uniqueidentifier` è possibile usare gli operatori di confronto. Quando si confrontano gli schemi di bit dei due valori, tuttavia, l'ordinamento non viene implementato. Le uniche operazioni consentite rispetto a un `uniqueidentifier` valore sono i confronti (=,  <>, \<, > , \<=, > =) e la verifica della presenza di valori NULL (IS NULL e is not null). Non sono ammessi altri operatori aritmetici.  
  
 Sia <xref:System.Guid> che <xref:System.Data.SqlTypes.SqlGuid> usano un metodo `CompareTo` per confrontare valori GUID diversi. `System.Guid.CompareTo` e `SqlTypes.SqlGuid.CompareTo` sono tuttavia implementati in modo diverso. <xref:System.Data.SqlTypes.SqlGuid> implementa `CompareTo` usando il comportamento di SQL Server, in cui gli ultimi 6 byte di un valore sono i più significativi. <xref:System.Guid> valuta tutti i 16 byte. L'esempio seguente illustra queste differenze di comportamento. La prima sezione del codice visualizza valori <xref:System.Guid> non ordinati, mentre la seconda sezione visualizza i valori <xref:System.Guid> ordinati. La terza sezione visualizza i valori <xref:System.Data.SqlTypes.SqlGuid> ordinati. L'output viene visualizzato sotto l'elenco codici.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 L'esempio produce i risultati seguenti.  
  
```output  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati SQL Server e ADO.NET](sql-server-data-types.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
