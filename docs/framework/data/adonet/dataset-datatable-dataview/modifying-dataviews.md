---
title: Modifica di oggetti DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 0b2bfd1b0490572e78c8ce365491a8d48db87684
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204567"
---
# <a name="modifying-dataviews"></a>Modifica di oggetti DataView
È possibile usare il <xref:System.Data.DataView> per aggiungere, eliminare o modificare righe di dati nella tabella sottostante. La possibilità di utilizzare **DataView** per modificare i dati nella tabella sottostante viene controllata impostando una delle tre proprietà booleane di **DataView**. Tali proprietà sono <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> e <xref:System.Data.DataView.AllowDelete%2A>. Sono impostate su **true** per impostazione predefinita.  
  
 Se **AllowNew** è **true**, è possibile usare il <xref:System.Data.DataView.AddNew%2A> metodo dell'oggetto **DataView** per creare un nuovo <xref:System.Data.DataRowView>oggetto. Si noti che una nuova riga non viene effettivamente aggiunta all'oggetto <xref:System.Data.DataTable> sottostante fino <xref:System.Data.DataRowView.EndEdit%2A> a quando non viene chiamato il metodo del **DataRowView** . Se viene <xref:System.Data.DataRowView.CancelEdit%2A> chiamato il metodo dell'oggetto **DataRowView** , la nuova riga viene eliminata. Si noti inoltre che è possibile modificare un solo **DataRowView** alla volta. Se si chiama il metodo **AddNew** o **BeginEdit** del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato in modo implicito sulla riga in sospeso. Quando viene chiamato **EndEdit** , le modifiche vengono applicate alla **DataTable** sottostante e possono essere sottoposte a commit o rifiutate in un secondo momento usando i metodi **AcceptChanges** o **RejectChanges** dell' **oggetto DataTable**, **DataSet**o  **Oggetto DataRow** . Se **AllowNew** è **false**, viene generata un'eccezione se si chiama il metodo **AddNew** del **DataRowView**.  
  
 Se **AllowEdit** è **true**, è possibile modificare il contenuto di un **DataRow** tramite il **DataRowView**. È possibile confermare le modifiche apportate alla riga sottostante usando **DataRowView. EndEdit** o rifiutare le modifiche usando **DataRowView. CancelEdit**. Notare che è possibile modificare solo una riga alla volta. Se si chiamano i metodi **AddNew** o **BeginEdit** del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato in modo implicito sulla riga in sospeso. Quando viene chiamato **EndEdit** , le modifiche proposte vengono inserite nella versione di riga **corrente** del **DataRow** sottostante e possono essere sottoposte a commit o rifiutate in un secondo momento usando i metodi **AcceptChanges** o **RejectChanges** del  **Oggetto DataTable**, **DataSet**o **DataRow** . Se **AllowEdit** è **false**, viene generata un'eccezione se si tenta di modificare un valore nell'oggetto **DataView**.  
  
 Quando viene modificato un oggetto **DataRowView** esistente, gli eventi del **DataTable** sottostante verranno comunque generati con le modifiche proposte. Si noti che se si chiama **EndEdit** o **CancelEdit** sul **DataRow**sottostante, le modifiche in sospeso verranno applicate o annullate indipendentemente dal fatto che **EndEdit** o **CancelEdit** venga chiamato sul **DataRowView**.  
  
 Se **proprietà AllowDelete** è **true**, è possibile eliminare righe dal **DataView** usando il metodo **Delete** dell'oggetto **DataView** o **DataRowView** e le righe vengono eliminate dall'oggetto **DataTable**sottostante. In un secondo momento è possibile eseguire il commit o rifiutare le eliminazioni usando **AcceptChanges** o **RejectChanges** rispettivamente. Se **proprietà AllowDelete** è **false**, viene generata un'eccezione se si chiama il metodo **Delete** di **DataView** o **DataRowView**.  
  
 Nell'esempio di codice seguente viene disabilitato l'utilizzo di **DataView** per eliminare righe e viene aggiunta una nuova riga alla tabella sottostante utilizzando il **DataView**.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [DataView](dataviews.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
