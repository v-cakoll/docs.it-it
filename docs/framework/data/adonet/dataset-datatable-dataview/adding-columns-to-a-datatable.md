---
title: Aggiunta di colonne a un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 77bf117b8835623d768f8b8b0ec3e4195174cad7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043955"
---
# <a name="adding-columns-to-a-datatable"></a>Aggiunta di colonne a un oggetto DataTable
Un <xref:System.Data.DataTable> oggetto contiene una raccolta <xref:System.Data.DataColumn> di oggetti a cui fa riferimento la proprietà **Columns** della tabella. Tale raccolta di colonne, insieme a eventuali vincoli, consente di definire lo schema, o struttura, della tabella.  
  
 Per creare oggetti **DataColumn** all'interno di una tabella, è possibile usare il costruttore **DataColumn** oppure chiamare il metodo **Add** della proprietà **Columns** della tabella, che è un <xref:System.Data.DataColumnCollection>oggetto. Il metodo **Add** accetta gli argomenti facoltativi **ColumnName**, **DataType**e **Expression** e crea un nuovo oggetto **DataColumn** come membro della raccolta. Accetta inoltre un oggetto **DataColumn** esistente e lo aggiunge alla raccolta e restituisce un riferimento alla **DataColumn** aggiunta, se richiesto. Poiché gli oggetti **DataTable** non sono specifici di alcuna origine dati, i tipi di .NET Framework vengono usati quando si specifica il tipo di dati di un oggetto **DataColumn**.  
  
 Nell'esempio seguente vengono aggiunte quattro colonne a un **oggetto DataTable**.  
  
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
  
 Nell'esempio si noti che le proprietà della colonna **CustID** sono impostate in modo da non consentire valori **DBNull** e vincolare i valori in modo che siano univoci. Tuttavia, se si definisce la colonna **CustID** come colonna chiave primaria della tabella, la proprietà **AllowDBNull** verrà impostata automaticamente su **false** e la proprietà **Unique** verrà impostata automaticamente su **true**. Per ulteriori informazioni, vedere [definizione delle chiavi primarie](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
> Se per una colonna non viene specificato un nome di colonna, alla colonna viene assegnato il nome predefinito incrementale Column*N,* che inizia con "Column1", quando viene aggiunto a DataColumnCollection. Si consiglia di evitare la convenzione di denominazione "Column*N*" quando si fornisce un nome di colonna, perché il nome fornito potrebbe entrare in conflitto con un nome di colonna predefinito esistentein DataColumnCollection. Se il nome fornito è già presente, viene generata un'eccezione.  
  
 Se si sta usando l'oggetto <xref:System.Xml.Linq.XElement> come proprietà <xref:System.Data.DataColumn.DataType%2A> di un oggetto <xref:System.Data.DataColumn> nell'oggetto <xref:System.Data.DataTable>, la serializzazione XML non funzionerà quando si legge nei dati. Ad esempio, se si scrive un oggetto <xref:System.Xml.XmlDocument> usando il metodo `DataTable.WriteXml`, durante la serializzazione in XML è presente un nodo padre aggiuntivo nell'oggetto <xref:System.Xml.Linq.XElement>. Per risolvere questo problema, usare il tipo <xref:System.Data.SqlTypes.SqlXml> invece dell'oggetto <xref:System.Xml.Linq.XElement>. `ReadXml` e `WriteXml` funzionano correttamente con l'oggetto <xref:System.Data.SqlTypes.SqlXml>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
