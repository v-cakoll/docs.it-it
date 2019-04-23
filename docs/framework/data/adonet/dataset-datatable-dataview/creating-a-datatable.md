---
title: Creazione di un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112385"
---
# <a name="creating-a-datatable"></a>Creazione di un oggetto DataTable
È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.  
  
 È possibile creare un **DataTable** oggetto utilizzando l'oggetto appropriato **DataTable** costruttore. È possibile aggiungerlo al **set di dati** tramite il **Add** metodo deve essere aggiunto il **DataTable** dell'oggetto **tabelle** raccolta.  
  
 È anche possibile creare **DataTable** oggetti all'interno di un **set di dati** utilizzando il **riempire** o **FillSchema** metodi del  **DataAdapter** oggetto, o da una predefinito o inferito XML schema usando il **ReadXml**, **ReadXmlSchema**, oppure **InferXmlSchema** i metodi del **set di dati**. Si noti che dopo aver aggiunto un **DataTable** come membro delle **tabelle** raccolta di uno **set di dati**, non è possibile aggiungere alla raccolta di tabelle di qualsiasi altro **Set di dati**.  
  
 Quando si crea prima di tutto una **DataTable**, che non è uno schema (vale a dire una struttura). Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> gli oggetti per il **colonne** insieme della tabella. È anche possibile definire una colonna chiave primaria per la tabella e creare e aggiungere **vincolo** gli oggetti per il **vincoli** insieme della tabella. Dopo aver definito lo schema per un **DataTable**, è possibile aggiungere le righe di dati alla tabella tramite l'aggiunta **DataRow** oggetti per il **righe** insieme della tabella.  
  
 Non è necessario fornire un valore per il <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un' **DataTable**; è possibile specificare la proprietà in un secondo momento, oppure è possibile lasciarla vuota. Tuttavia, quando si aggiunge una tabella senza un **TableName** valore a un **set di dati**, la tabella verrà assegnato un nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.  
  
> [!NOTE]
>  È consigliabile evitare il "tabella*N*" convenzione di denominazione quando si fornisce un **TableName** valore, poiché il nome immesso sia in conflitto con un nome di tabella predefinito esistente nel **set di dati** . Se il nome fornito è già presente, viene generata un'eccezione.  
  
 L'esempio seguente crea un'istanza di un **DataTable** dell'oggetto e le assegna il nome "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 L'esempio seguente crea un'istanza di un **DataTable** aggiungendola alle **tabelle** raccolta di un **set di dati**.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
