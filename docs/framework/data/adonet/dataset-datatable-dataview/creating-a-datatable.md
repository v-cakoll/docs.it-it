---
title: Creazione di un oggetto DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 68f8272aa0f525c04120f129057e6151e42ffee1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datatable"></a>Creazione di un oggetto DataTable
È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.  
  
 È possibile creare un **DataTable** oggetto, utilizzando i **DataTable** costruttore. È possibile aggiungerlo al **DataSet** utilizzando il **Aggiungi** metodo per aggiungerlo al **DataTable** dell'oggetto **tabelle** insieme.  
  
 È inoltre possibile creare **DataTable** oggetti all'interno di un **set di dati** utilizzando il **riempimento** o **FillSchema** metodi del  **DataAdapter** oggetto, o da un predefinito o inferito uno schema XML utilizzando il **ReadXml**, **ReadXmlSchema**, o **InferXmlSchema** metodi di **DataSet**. Si noti che dopo aver aggiunto un **DataTable** come membro del **tabelle** raccolta costituita da un **DataSet**, non è possibile aggiungere alla raccolta di tabelle di qualsiasi altro **DataSet**.  
  
 Quando si crea innanzitutto un **DataTable**, non è uno schema (ovvero, una struttura). Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> oggetti per il **colonne** insieme della tabella. È inoltre possibile definire una colonna chiave primaria per la tabella e creare e aggiungere **vincolo** oggetti per il **vincoli** insieme della tabella. Dopo aver definito lo schema per un **DataTable**, è possibile aggiungere righe di dati alla tabella aggiungendo **DataRow** oggetti per il **righe** insieme della tabella.  
  
 Non è necessario fornire un valore per il <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un **DataTable**; è possibile specificare la proprietà in un secondo momento, oppure è possibile lasciare vuoto. Tuttavia, quando si aggiunge una tabella senza un **TableName** valore un **DataSet**, la tabella verrà assegnato un nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.  
  
> [!NOTE]
>  È consigliabile evitare di "tabella*N*" convenzione di denominazione quando si fornisce un **TableName** valore, poiché il nome sia in conflitto con un nome di tabella predefinito esistente nel **set di dati** . Se il nome fornito è già presente, viene generata un'eccezione.  
  
 L'esempio seguente crea un'istanza di un **DataTable** dell'oggetto e viene assegnato il nome "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 L'esempio seguente crea un'istanza di un **DataTable** aggiungendolo al **tabelle** raccolta di un **DataSet**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
