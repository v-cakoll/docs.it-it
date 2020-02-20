---
title: Mapping dei tipi di dati SQL Server e ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: f727c69b1dd5c23c6a89911005256de70255fd4c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452331"
---
# <a name="sql-server-data-types-and-adonet"></a>Mapping dei tipi di dati SQL Server e ADO.NET
SQL Server e .NET Framework sono basati su sistemi di tipi diversi che possono comportare una potenziale perdita di dati. Per mantenere l'integrità dei dati, il provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>) fornisce metodi delle funzioni di accesso tipizzate per l'uso dei dati SQL Server. È possibile usare le enumerazioni nelle classi <xref:System.Data.SqlDbType> per specificare i tipi di dati <xref:System.Data.SqlClient.SqlParameter>.  
  
 Per ulteriori informazioni e per una tabella in cui vengono descritti i mapping dei tipi di dati tra SQL Server e .NET Framework tipi di dati, vedere [SQL Server mapping dei](../sql-server-data-type-mappings.md)tipi di dati.  
  
 In SQL Server 2008 vengono introdotti nuovi tipi di dati progettati per soddisfare le esigenze aziendali di uso di dati relativi a data e ora, strutturati, semistrutturati e non strutturati. Questi tipi sono illustrati nella documentazione online di SQL Server 2008.  
  
 I tipi di dati SQL Server disponibili per l'uso nell'applicazione dipendono dalla versione di SQL Server in uso. Per altre informazioni, vedere la versione rilevante della documentazione online di SQL Server nella tabella seguente.  
  
 **Documentazione di SQL Server**  
  
1. [Tipi di dati (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [SqlTypes e DataSet](sqltypes-and-the-dataset.md)  
 Viene descritto il supporto dei tipi per `SqlTypes` in `DataSet`.  
  
 [Gestione dei valori null](handling-null-values.md)  
 Viene illustrato come usare i valori null e la logica a tre valori.  
  
 [Confronto tra GUID e valori uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Viene illustrato come usare valori GUID e uniqueidentifier in SQL Server e in .NET Framework.  
  
 [Dati relativi a data e ora](date-and-time-data.md)  
 Viene descritto come usare i nuovi tipi di dati relativi a data e ora in SQL Server 2008.  
  
 [Tipi di grandi dimensioni definiti dall'utente](large-udts.md)  
 Viene illustrato come recuperare i dati dai tipi UDT con valori di grandi dimensioni introdotti in SQL Server 2008.  
  
 [Dati XML in SQL Server](xml-data-in-sql-server.md)  
 Viene descritto come usare i dati XML recuperati da SQL Server.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Data.DataSet>  
 Vengono descritti la classe `DataSet` e tutti i relativi membri.  
  
 <xref:System.Data.SqlTypes>  
 Vengono descritti lo spazio dei nomi `SqlTypes` e tutti i relativi membri.  
  
 <xref:System.Data.SqlDbType>  
 Vengono descritti l'enumerazione `SqlDbType` e tutti i relativi membri.  
  
 <xref:System.Data.DbType>  
 Vengono descritti l'enumerazione `DbType` e tutti i relativi membri.  
  
## <a name="see-also"></a>Vedere anche

- [Mapping dei tipi di dati SQL Server](../sql-server-data-type-mappings.md)
- [Configurazione di parametri e tipi di dati dei parametri](../configuring-parameters-and-parameter-data-types.md)
- [Parametri valutati a livello di tabella](table-valued-parameters.md)
- [Dati binari e con valori elevati SQL Server](sql-server-binary-and-large-value-data.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
