---
title: Aggiunta di colonne a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 2e7008f6693d7d76520a7ff6ae9172e28e4990c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207006"
---
# <a name="adding-columns-to-a-datatable"></a>Aggiunta di colonne a un oggetto DataTable
Oggetto <xref:System.Data.DataTable> contiene una raccolta di <xref:System.Data.DataColumn> gli oggetti a cui fanno riferimento le **colonne** proprietà della tabella. Tale raccolta di colonne, insieme a eventuali vincoli, consente di definire lo schema, o struttura, della tabella.  
  
 Crei **DataColumn** oggetti all'interno di una tabella utilizzando il **DataColumn** costruttore, oppure chiamando il **Aggiungi** metodo del **colonne**proprietà della tabella, ovvero un <xref:System.Data.DataColumnCollection>. Il **Add** metodo accetta facoltativo **nomecolonna**, **DataType**, e **espressione** argomenti e crea un nuovo  **DataColumn** come membro della raccolta. L'attività accetta inoltre un oggetto esistente **DataColumn** dell'oggetto e lo aggiunge alla raccolta e restituisce un riferimento all'oggetto aggiunto **DataColumn** se richiesto. In quanto **DataTable** gli oggetti non sono specifici di qualsiasi origine dati, i tipi di .NET Framework vengono usati quando si specifica il tipo di dati di un **DataColumn**.  
  
 L'esempio seguente aggiunge quattro colonne a un **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 Nell'esempio, si noti che le proprietà per il **CustID** colonna sono impostate per non consentire **DBNull** valori e per vincolare i valori siano univoci. Tuttavia, se si definisce la **CustID** colonna come colonna chiave primaria della tabella, il **AllowDBNull** verrà automaticamente impostata su **false** e il **Unique** verrà automaticamente impostata su **true**. Per altre informazioni, vedere [definizione di chiavi primarie](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Se non viene fornito un nome di colonna per una colonna, la colonna viene assegnata il nome predefinito incrementale della colonna*N,* a partire da "Column1", quando viene aggiunto per il **DataColumnCollection**. Si consiglia di evitare la convenzione di denominazione "colonna*N*" quando si fornisce un nome di colonna, perché il nome fornito sia in conflitto con un nome di colonna predefinito esistente nel **DataColumnCollection**. Se il nome fornito è già presente, viene generata un'eccezione.  
  
 Se si sta usando l'oggetto <xref:System.Xml.Linq.XElement> come proprietà <xref:System.Data.DataColumn.DataType%2A> di un oggetto <xref:System.Data.DataColumn> nell'oggetto <xref:System.Data.DataTable>, la serializzazione XML non funzionerà quando si legge nei dati. Ad esempio, se si scrive un oggetto <xref:System.Xml.XmlDocument> usando il metodo `DataTable.WriteXml`, durante la serializzazione in XML è presente un nodo padre aggiuntivo nell'oggetto <xref:System.Xml.Linq.XElement>. Per risolvere questo problema, usare il tipo <xref:System.Data.SqlTypes.SqlXml> invece dell'oggetto <xref:System.Xml.Linq.XElement>. `ReadXml` e `WriteXml` funzionano correttamente con l'oggetto <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
