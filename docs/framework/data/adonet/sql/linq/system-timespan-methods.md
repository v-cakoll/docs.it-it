---
title: Metodi System.TimeSpan
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: a3f3c82f9f8db4b72588f165ed4d897b974eb076
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539909"
---
# <a name="systemtimespan-methods"></a>Metodi System.TimeSpan
Il supporto dei membri per <xref:System.TimeSpan?displayProperty=nameWithType> dipende molto dalle versioni di .NET Framework e di Microsoft SQL Server in uso.  
  
 Quando un metodo, una proprietà o un operatore non è supportato, significa che LINQ to SQL non può eseguire la conversione del membro per l'esecuzione in SQL Server. È comunque possibile usare questi membri nel codice. Essi devono tuttavia essere valutati prima che la query venga convertita in Transact-SQL o dopo che i risultati siano stati recuperati dal database.  
  
## <a name="previous-limitations"></a>Limitazioni precedenti  
 Quando si usa LINQ to SQL con versioni di .NET Framework precedenti a .NET Framework 3.5 SP1, non è possibile eseguire il mapping di campi dei database di SQL Server a <xref:System.TimeSpan?displayProperty=nameWithType>. Sono tuttavia supportate operazioni su <xref:System.TimeSpan>, in quanto è possibile che i valori <xref:System.TimeSpan> vengano restituiti da una sottrazione <xref:System.DateTime> o vengano introdotti in un'espressione come un valore letterale o una variabile associata.  
  
## <a name="supported-systemtimespan-member-support"></a>Supporto per membri System. TimeSpan supportato

 I metodi, le proprietà e gli operatori seguenti supportati da LINQ to SQL sono disponibili per l'uso nelle query LINQ to SQL. Una volta eseguito il mapping nel modello a oggetti o nel file di mapping esterno, LINQ to SQL consente di chiamare numerosi membri <xref:System.TimeSpan?displayProperty=nameWithType> nelle query LINQ to SQL.  
  
|Metodi <xref:System.TimeSpan> supportati|Operatori <xref:System.TimeSpan> supportati|Proprietà <xref:System.TimeSpan> supportate|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
>  Per eseguire il mapping di <xref:System.TimeSpan?displayProperty=nameWithType> a una colonna `TIME` SQL con LINQ to SQL è necessario disporre di .NET Framework 3.5 SP1 o versione successiva. Il tipo di dati `TIME` SQL è disponibile solo in Microsoft SQL Server 2008 e versioni successive.  
  
### <a name="addition-and-subtraction"></a>Aggiunta e sottrazione  
 Sebbene il tipo <xref:System.TimeSpan?displayProperty=nameWithType> CLR supporti l'aggiunta e la sottrazione, il tipo `TIME` SQL non supporta queste operazioni. Per questo motivo, le query LINQ to SQL genereranno errori se viene eseguito un tentativo di aggiunta e sottrazione quando sono mappate al tipo `TIME` SQL. È possibile trovare altre considerazioni per l'utilizzo di tipi date e time SQL nel [Mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
## <a name="see-also"></a>Vedere anche
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Mapping del tipo SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Tipi di dati e funzioni](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
