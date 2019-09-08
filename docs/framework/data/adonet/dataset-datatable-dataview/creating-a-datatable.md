---
title: Creazione di un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: e48359041f92e7b534513aa461a293a822bede19
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786496"
---
# <a name="creating-a-datatable"></a>Creazione di un oggetto DataTable
È possibile creare una <xref:System.Data.DataTable>, che rappresenta una tabella di dati relazionali in memoria, e usarla in modo indipendente oppure usarla tramite altri oggetti di .NET Framework, in genere come membro di un <xref:System.Data.DataSet>.  
  
 È possibile creare un oggetto **DataTable** usando il costruttore **DataTable** appropriato. È possibile aggiungerlo al **set di dati** usando il metodo **Add** per aggiungerlo alla raccolta **Tables** dell'oggetto **DataTable** .  
  
 È anche possibile creare oggetti **DataTable** all'interno di un **set di dati** usando i metodi **Fill** o **FillSchema** dell'oggetto **DataAdapter** oppure da un XML Schema predefinito o dedotto usando **ReadXml**, **ReadXmlSchema** o metodi **InferXmlSchema** del set di **dati**. Si noti che dopo aver aggiunto un **DataTable** come membro della raccolta **Tables** di un **set di dati**, non è possibile aggiungerlo alla raccolta di tabelle di qualsiasi altro **set di dati**.  
  
 Quando si crea una **DataTable**per la prima volta, non è presente uno schema, ovvero una struttura. Per definire lo schema della tabella, è necessario creare e aggiungere <xref:System.Data.DataColumn> oggetti alla raccolta **Columns** della tabella. È inoltre possibile definire una colonna chiave primaria per la tabella e creare e aggiungere oggetti **Constraint** alla raccolta **Constraints** della tabella. Dopo aver definito lo schema per una **DataTable**, è possibile aggiungere righe di dati alla tabella aggiungendo oggetti **DataRow** alla raccolta **Rows** della tabella.  
  
 Non è necessario fornire un valore per la <xref:System.Data.DataTable.TableName%2A> proprietà quando si crea un **oggetto DataTable**; è possibile specificare la proprietà in un altro momento oppure lasciarlo vuoto. Tuttavia, quando si aggiunge una tabella senza un valore **TableName** a un **set di dati**, alla tabella verrà assegnato il nome predefinito incrementale Table*N*, che inizia con "Table" per Table0.  
  
> [!NOTE]
> Si consiglia di evitare la convenzione di denominazione "Table*N*" quando si fornisce un valore **TableName** , perché il nome fornito potrebbe entrare in conflitto con un nome di tabella predefinito esistente nel **set di dati**. Se il nome fornito è già presente, viene generata un'eccezione.  
  
 Nell'esempio seguente viene creata un'istanza di un oggetto **DataTable** a cui viene assegnato il nome "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 Nell'esempio seguente viene creata un'istanza di un **oggetto DataTable** aggiungendola alla raccolta **Tables** di un **set di dati**.  
  
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
- [DataTable](datatables.md)
- [Popolamento di un set di dati da un oggetto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
