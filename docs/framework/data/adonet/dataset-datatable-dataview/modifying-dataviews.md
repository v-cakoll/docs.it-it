---
title: Modifica di oggetti DataView
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
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0a8478e9b21c6c2abdc02677305e468109e7b9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-dataviews"></a>Modifica di oggetti DataView
È possibile usare il <xref:System.Data.DataView> per aggiungere, eliminare o modificare righe di dati nella tabella sottostante. La possibilità di utilizzare il **DataView** per modificare i dati nella tabella sottostante è controllata dall'impostazione di una delle tre proprietà Boolean del **DataView**. Tali proprietà sono <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> e <xref:System.Data.DataView.AllowDelete%2A>. Sono impostati su **true** per impostazione predefinita.  
  
 Se **AllowNew** è **true**, è possibile utilizzare il <xref:System.Data.DataView.AddNew%2A> metodo il **DataView** per creare un nuovo <xref:System.Data.DataRowView>. Si noti che non è una nuova riga effettivamente aggiunti alla sottostante <xref:System.Data.DataTable> fino a quando il <xref:System.Data.DataRowView.EndEdit%2A> metodo il **DataRowView** viene chiamato. Se il <xref:System.Data.DataRowView.CancelEdit%2A> metodo il **DataRowView** viene chiamato, la nuova riga viene eliminata. Si noti inoltre che è possibile modificare solo una **DataRowView** alla volta. Se si chiama il **AddNew** o **BeginEdit** metodo il **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso. Quando **EndEdit** viene chiamato, le modifiche vengono applicate al sottostante **DataTable** e versioni successive possono essere eseguito il commit o rifiutate tramite il **AcceptChanges** o  **RejectChanges** metodi di **DataTable**, **DataSet**, o **DataRow** oggetto. Se **AllowNew** è **false**, viene generata un'eccezione se si chiama il **AddNew** metodo il **DataRowView**.  
  
 Se **AllowEdit** è **true**, è possibile modificare il contenuto di un **DataRow** tramite il **DataRowView**. È possibile confermare le modifiche apportate alla riga sottostante mediante **DataRowView. EndEdit** o rifiutare le modifiche utilizzando **CancelEdit**. Notare che è possibile modificare solo una riga alla volta. Se si chiama il **AddNew** o **BeginEdit** metodi di **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso. Quando **EndEdit** viene chiamato, le modifiche proposte vengono inserite nel **corrente** versione di riga dell'oggetto sottostante **DataRow** e versioni successive è possibile confermarle o rifiutarle utilizzando il  **AcceptChanges** o **RejectChanges** metodi di **DataTable**, **DataSet**, o **DataRow** oggetto. Se **AllowEdit** è **false**, viene generata un'eccezione se si tenta di modificare un valore di **DataView**.  
  
 Quando un oggetto esistente **DataRowView** viene modificato, gli eventi dell'oggetto sottostante **DataTable** vengono ancora generati con le modifiche proposte. Si noti che se si chiama **EndEdit** o **CancelEdit** sull'oggetto sottostante **DataRow**, in sospeso le modifiche verranno applicate o annullate indipendentemente dal fatto che  **EndEdit** o **CancelEdit** viene chiamato sul **DataRowView**.  
  
 Se **AllowDelete** è **true**, è possibile eliminare righe dal **DataView** utilizzando il **eliminare** metodo il **DataView**  o **DataRowView** oggetto e le righe vengono eliminate dalla classe **DataTable**. È possibile in un secondo momento eseguire il commit o rifiutare le eliminazioni utilizzando **AcceptChanges** o **RejectChanges** rispettivamente. Se **AllowDelete** è **false**, viene generata un'eccezione se si chiama il **eliminare** metodo il **DataView** o  **DataRowView**.  
  
 Disattiva l'utilizzo di esempio di codice seguente il **DataView** per eliminare righe e aggiunge una nuova riga alla tabella sottostante mediante la **DataView**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
