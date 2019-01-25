---
title: Modifica di oggetti DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: f892a371ed23a810f71ef5a51393de4145478c10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573244"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="f4f48-102">Modifica di oggetti DataView</span><span class="sxs-lookup"><span data-stu-id="f4f48-102">Modifying DataViews</span></span>
<span data-ttu-id="f4f48-103">È possibile usare il <xref:System.Data.DataView> per aggiungere, eliminare o modificare righe di dati nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="f4f48-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="f4f48-104">La possibilità di usare la **DataView** per modificare i dati nella tabella sottostante viene controllata impostando una delle tre proprietà Boolean del **DataView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="f4f48-105">Tali proprietà sono <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> e <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4f48-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="f4f48-106">Vengono impostate su **true** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f4f48-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="f4f48-107">Se **AllowNew** viene **true**, è possibile usare il <xref:System.Data.DataView.AddNew%2A> metodo del **DataView** per creare un nuovo <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="f4f48-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="f4f48-108">Si noti che una nuova riga non viene effettivamente aggiunta al sottostante <xref:System.Data.DataTable> fino a quando non la <xref:System.Data.DataRowView.EndEdit%2A> metodo per il **DataRowView** viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f4f48-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="f4f48-109">Se il <xref:System.Data.DataRowView.CancelEdit%2A> metodo per il **DataRowView** viene chiamato, la nuova riga viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f4f48-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="f4f48-110">Si noti anche che è possibile modificare solo una **DataRowView** alla volta.</span><span class="sxs-lookup"><span data-stu-id="f4f48-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="f4f48-111">Se si chiama il **AddNew** o **BeginEdit** metodo per il **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f4f48-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="f4f48-112">Quando **EndEdit** viene chiamato, le modifiche vengono applicate a sottostante **DataTable** e versioni successive possono essere eseguito il commit o rifiutate tramite il **AcceptChanges** o  **RejectChanges** metodi del **DataTable**, **DataSet**, oppure **DataRow** oggetto.</span><span class="sxs-lookup"><span data-stu-id="f4f48-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="f4f48-113">Se **AllowNew** viene **false**, viene generata un'eccezione se si chiama il **AddNew** metodo il **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="f4f48-114">Se **AllowEdit** viene **true**, è possibile modificare il contenuto di un **DataRow** tramite i **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="f4f48-115">È possibile confermare le modifiche apportate alla riga sottostante mediante **DataRowView. EndEdit** o rifiutare le modifiche utilizzando **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="f4f48-116">Notare che è possibile modificare solo una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="f4f48-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="f4f48-117">Se si chiama il **AddNew** oppure **BeginEdit** metodi del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato implicitamente per la riga in sospeso.</span><span class="sxs-lookup"><span data-stu-id="f4f48-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="f4f48-118">Quando **EndEdit** viene chiamato, le modifiche proposte vengono inserite nel **corrente** versione di riga dell'oggetto sottostante **DataRow** e in seguito può essere eseguito il commit o rifiutate tramite il  **AcceptChanges** oppure **RejectChanges** metodi del **DataTable**, **set di dati**, o **DataRow** oggetto.</span><span class="sxs-lookup"><span data-stu-id="f4f48-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="f4f48-119">Se **AllowEdit** viene **false**, viene generata un'eccezione se si prova a modificare un valore di **DataView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="f4f48-120">Quando un oggetto esistente **DataRowView** viene modificato, gli eventi dell'oggetto sottostante **DataTable** vengono ancora generati con le modifiche proposte.</span><span class="sxs-lookup"><span data-stu-id="f4f48-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="f4f48-121">Si noti che se si chiama **EndEdit** oppure **CancelEdit** sottostante **DataRow**, in sospeso verranno applicate o annullate indipendentemente dal fatto che le modifiche  **EndEdit** oppure **CancelEdit** viene chiamato per il **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="f4f48-122">Se **AllowDelete** viene **true**, è possibile eliminare righe dal **DataView** utilizzando il **Elimina** metodo del **DataView**  oppure **DataRowView** oggetto e le righe vengono eliminate da sottostante **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="f4f48-123">In un secondo momento è possibile eseguire il commit o rifiutare le eliminazioni utilizzando **AcceptChanges** oppure **RejectChanges** rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="f4f48-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="f4f48-124">Se **AllowDelete** viene **false**, viene generata un'eccezione se si chiama il **Elimina** metodo il **DataView** o  **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="f4f48-125">L'esempio di codice seguente disabilita usando il **DataView** per eliminare righe e aggiunge una nuova riga alla tabella sottostante mediante il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="f4f48-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f4f48-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4f48-126">See also</span></span>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="f4f48-127">DataView</span><span class="sxs-lookup"><span data-stu-id="f4f48-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="f4f48-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f4f48-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
