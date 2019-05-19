---
title: Oracle e ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 012a5b55d052f5f06da5c152da79f4676b2bff4e
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877954"
---
# <a name="oracle-and-adonet"></a>Oracle e ADO.NET
> [!NOTE]
>  I tipi in <xref:System.Data.OracleClient> sono deprecati. I tipi restano supportati nella versione corrente di .NET Framework, ma saranno rimossi in una versione futura. Microsoft consiglia di usare un provider Oracle di terze parti.  
  
 Questa sezione descrive le funzionalità e i comportamenti specifici per il Provider di dati .NET Framework per Oracle.  
  
 Il Provider di dati .NET Framework per Oracle fornisce l'accesso a un database Oracle mediante l'interfaccia OCI (Oracle Call Interface) del software Client Oracle. La funzionalità del provider di dati è progettata per essere simile a quella dei provider di dati .NET Framework per SQL Server, OLE DB e ODBC.  
  
 Per usare il Provider di dati .NET Framework per Oracle, è necessario fare riferimento a un'applicazione di <xref:System.Data.OracleClient> dello spazio dei nomi come indicato di seguito:  
  
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
 Vengono descritti i requisiti per l'uso di Provider di dati .NET Framework per Oracle e descrive alcuni problemi da tenere in considerazione quando viene usato.  
  
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
 Vengono descritte le tecniche che consentono di scrivere codice sicuro quando si usa ADO.NET.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Viene descritto come creare e usare `DataSets`, `DataSets` tipizzati, `DataTables` e `DataViews`.  
  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Viene descritto come usare i dati in ADO.NET.  
  
 [SQL Server e ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Viene descritto come usare le funzionalità e le caratteristiche specifiche di SQL Server.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Vengono descritte le classi generiche che consentono di scrivere codice indipendente dal provider in ADO.NET.  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
