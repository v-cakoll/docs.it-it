---
title: Modifica di oggetti DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3b1e0cbfc6118ad9ca670f5d91183b78b2c99d89
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44268536"
---
# <a name="modifying-dataviews"></a>Modifica di oggetti DataView
È possibile usare il <xref:System.Data.DataView> per aggiungere, eliminare o modificare righe di dati nella tabella sottostante. La possibilità di usare la **DataView** per modificare i dati nella tabella sottostante viene controllata impostando una delle tre proprietà Boolean del **DataView**. Tali proprietà sono <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> e <xref:System.Data.DataView.AllowDelete%2A>. Vengono impostate su **true** per impostazione predefinita.  
  
 Se **AllowNew** viene **true**, è possibile usare il <xref:System.Data.DataView.AddNew%2A> metodo del **DataView** per creare un nuovo <xref:System.Data.DataRowView>. Si noti che una nuova riga non viene effettivamente aggiunta al sottostante <xref:System.Data.DataTable> fino a quando non la <xref:System.Data.DataRowView.EndEdit%2A> metodo per il **DataRowView** viene chiamato. Se il <xref:System.Data.DataRowView.CancelEdit%2A> metodo per il **DataRowView** viene chiamato, la nuova riga viene eliminata. Si noti anche che è possibile modificare solo una **DataRowView** alla volta. Se si chiama il **AddNew** o **BeginEdit** metodo per il **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso. Quando **EndEdit** viene chiamato, le modifiche vengono applicate a sottostante **DataTable** e versioni successive possono essere eseguito il commit o rifiutate tramite il **AcceptChanges** o  **RejectChanges** metodi del **DataTable**, **DataSet**, oppure **DataRow** oggetto. Se **AllowNew** viene **false**, viene generata un'eccezione se si chiama il **AddNew** metodo il **DataRowView**.  
  
 Se **AllowEdit** viene **true**, è possibile modificare il contenuto di un **DataRow** tramite i **DataRowView**. È possibile confermare le modifiche apportate alla riga sottostante mediante **DataRowView. EndEdit** o rifiutare le modifiche utilizzando **CancelEdit**. Notare che è possibile modificare solo una riga alla volta. Se si chiama il **AddNew** oppure **BeginEdit** metodi del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso. Quando **EndEdit** viene chiamato, le modifiche proposte vengono inserite nel **corrente** versione di riga dell'oggetto sottostante **DataRow** e in seguito può essere eseguito il commit o rifiutate tramite il  **AcceptChanges** oppure **RejectChanges** metodi del **DataTable**, **set di dati**, o **DataRow** oggetto. Se **AllowEdit** viene **false**, viene generata un'eccezione se si prova a modificare un valore di **DataView**.  
  
 Quando un oggetto esistente **DataRowView** viene modificato, gli eventi dell'oggetto sottostante **DataTable** vengono ancora generati con le modifiche proposte. Si noti che se si chiama **EndEdit** oppure **CancelEdit** sottostante **DataRow**, in sospeso verranno applicate o annullate indipendentemente dal fatto che le modifiche  **EndEdit** oppure **CancelEdit** viene chiamato per il **DataRowView**.  
  
 Se **AllowDelete** viene **true**, è possibile eliminare righe dal **DataView** utilizzando il **Elimina** metodo del **DataView**  oppure **DataRowView** oggetto e le righe vengono eliminate da sottostante **DataTable**. In un secondo momento è possibile eseguire il commit o rifiutare le eliminazioni utilizzando **AcceptChanges** oppure **RejectChanges** rispettivamente. Se **AllowDelete** viene **false**, viene generata un'eccezione se si chiama il **Elimina** metodo il **DataView** o  **DataRowView**.  
  
 L'esempio di codice seguente disabilita usando il **DataView** per eliminare righe e aggiunge una nuova riga alla tabella sottostante mediante il **DataView**.  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
