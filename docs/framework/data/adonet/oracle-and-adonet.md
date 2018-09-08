---
title: Oracle e ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 9a60499674f0192bb7589f227bffb6f907f682d9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084598"
---
# <a name="oracle-and-adonet"></a>Oracle e ADO.NET
> [!NOTE]
>  I tipi in <xref:System.Data.OracleClient> sono deprecati. I tipi restano supportati nella versione corrente di .NET Framework, ma saranno rimossi in una versione futura. Microsoft consiglia di usare un provider Oracle di terze parti.  
  
 Contenuto della sezione vengono descritte le caratteristiche e i comportamenti specifici del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle.  
  
 Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle fornisce l'accesso a un database Oracle mediante l'interfaccia OCI (Oracle Call Interface) del software client Oracle. La funzionalità del provider di dati è progettata per essere simile a quella del [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provider di dati per SQL Server, OLE DB e ODBC.  
  
 Per usare il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle, è necessario che l'applicazione faccia riferimento allo spazio dei nomi <xref:System.Data.OracleClient> come indicato di seguito:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Quando si compila il codice, inoltre, è necessario includere un riferimento alla DLL. Ad esempio, se si compila un programma C#, la riga di comando deve includere:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>In questa sezione  
 [Requisiti di sistema](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Vengono descritti i requisiti e i problemi relativi all'utilizzo del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle.  
  
 [Oggetti BFILE Oracle](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Viene descritta la classe <xref:System.Data.OracleClient.OracleBFile> usata per il tipo di dati BFILE Oracle.  
  
 [Oggetti LOB Oracle](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Viene descritta la classe <xref:System.Data.OracleClient.OracleLob> usata per il tipo di dati LOB Oracle.  
  
 [Oggetti REF CURSOR Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Viene descritto il supporto del tipo di dati REF CURSOR Oracle.  
  
 [OracleTypes](../../../../docs/framework/data/adonet/oracletypes.md)  
 Vengono descritte le strutture utilizzabili con i tipi di dati Oracle, inclusi tipi <xref:System.Data.OracleClient.OracleNumber> e <xref:System.Data.OracleClient.OracleString>.  
  
 [Sequenze Oracle](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Viene descritto il supporto per il recupero dei valori chiave di sequenze di Oracle generati dal server.  
  
 [Mapping dei tipi di dati Oracle](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Vengono presentati i tipi di dati Oracle e i relativi mapping alla classe <xref:System.Data.OracleClient.OracleDataReader>.  
  
 [Transazioni distribuite Oracle](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Viene descritto come l'oggetto <xref:System.Data.OracleClient.OracleConnection>, in presenza di una transazione attiva, esegue l'inserimento automatico nella transazione distribuita.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Protezione delle applicazioni ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Vengono descritte le tecniche che consentono di scrivere codice protetto quando si usa [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Viene descritto come creare e usare `DataSets`, `DataSets` tipizzati, `DataTables` e `DataViews`.  
  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Viene descritto come usare i dati in ADO.NET.  
  
 [SQL Server e ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Viene descritto come usare le funzionalità specifiche di SQL Server.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Vengono descritte le classi generiche che consentono di scrivere codice indipendente dal provider in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
