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
# <a name="modifying-dataviews"></a><span data-ttu-id="92481-102">Modifica di oggetti DataView</span><span class="sxs-lookup"><span data-stu-id="92481-102">Modifying DataViews</span></span>
<span data-ttu-id="92481-103">È possibile usare il <xref:System.Data.DataView> per aggiungere, eliminare o modificare righe di dati nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="92481-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="92481-104">La possibilità di utilizzare **DataView** per modificare i dati nella tabella sottostante viene controllata impostando una delle tre proprietà booleane di **DataView**.</span><span class="sxs-lookup"><span data-stu-id="92481-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="92481-105">Tali proprietà sono <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> e <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="92481-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="92481-106">Sono impostate su **true** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="92481-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="92481-107">Se **AllowNew** è **true**, è possibile usare il <xref:System.Data.DataView.AddNew%2A> metodo dell'oggetto **DataView** per creare un nuovo <xref:System.Data.DataRowView>oggetto.</span><span class="sxs-lookup"><span data-stu-id="92481-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="92481-108">Si noti che una nuova riga non viene effettivamente aggiunta all'oggetto <xref:System.Data.DataTable> sottostante fino <xref:System.Data.DataRowView.EndEdit%2A> a quando non viene chiamato il metodo del **DataRowView** .</span><span class="sxs-lookup"><span data-stu-id="92481-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="92481-109">Se viene <xref:System.Data.DataRowView.CancelEdit%2A> chiamato il metodo dell'oggetto **DataRowView** , la nuova riga viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="92481-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="92481-110">Si noti inoltre che è possibile modificare un solo **DataRowView** alla volta.</span><span class="sxs-lookup"><span data-stu-id="92481-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="92481-111">Se si chiama il metodo **AddNew** o **BeginEdit** del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato in modo implicito sulla riga in sospeso.</span><span class="sxs-lookup"><span data-stu-id="92481-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="92481-112">Quando viene chiamato **EndEdit** , le modifiche vengono applicate alla **DataTable** sottostante e possono essere sottoposte a commit o rifiutate in un secondo momento usando i metodi **AcceptChanges** o **RejectChanges** dell' **oggetto DataTable**, **DataSet**o  **Oggetto DataRow** .</span><span class="sxs-lookup"><span data-stu-id="92481-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="92481-113">Se **AllowNew** è **false**, viene generata un'eccezione se si chiama il metodo **AddNew** del **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="92481-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="92481-114">Se **AllowEdit** è **true**, è possibile modificare il contenuto di un **DataRow** tramite il **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="92481-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="92481-115">È possibile confermare le modifiche apportate alla riga sottostante usando **DataRowView. EndEdit** o rifiutare le modifiche usando **DataRowView. CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="92481-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="92481-116">Notare che è possibile modificare solo una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="92481-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="92481-117">Se si chiamano i metodi **AddNew** o **BeginEdit** del **DataRowView** mentre è presente una riga in sospeso, **EndEdit** viene chiamato in modo implicito sulla riga in sospeso.</span><span class="sxs-lookup"><span data-stu-id="92481-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="92481-118">Quando viene chiamato **EndEdit** , le modifiche proposte vengono inserite nella versione di riga **corrente** del **DataRow** sottostante e possono essere sottoposte a commit o rifiutate in un secondo momento usando i metodi **AcceptChanges** o **RejectChanges** del  **Oggetto DataTable**, **DataSet**o **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="92481-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="92481-119">Se **AllowEdit** è **false**, viene generata un'eccezione se si tenta di modificare un valore nell'oggetto **DataView**.</span><span class="sxs-lookup"><span data-stu-id="92481-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="92481-120">Quando viene modificato un oggetto **DataRowView** esistente, gli eventi del **DataTable** sottostante verranno comunque generati con le modifiche proposte.</span><span class="sxs-lookup"><span data-stu-id="92481-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="92481-121">Si noti che se si chiama **EndEdit** o **CancelEdit** sul **DataRow**sottostante, le modifiche in sospeso verranno applicate o annullate indipendentemente dal fatto che **EndEdit** o **CancelEdit** venga chiamato sul **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="92481-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="92481-122">Se **proprietà AllowDelete** è **true**, è possibile eliminare righe dal **DataView** usando il metodo **Delete** dell'oggetto **DataView** o **DataRowView** e le righe vengono eliminate dall'oggetto **DataTable**sottostante.</span><span class="sxs-lookup"><span data-stu-id="92481-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="92481-123">In un secondo momento è possibile eseguire il commit o rifiutare le eliminazioni usando **AcceptChanges** o **RejectChanges** rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="92481-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="92481-124">Se **proprietà AllowDelete** è **false**, viene generata un'eccezione se si chiama il metodo **Delete** di **DataView** o **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="92481-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="92481-125">Nell'esempio di codice seguente viene disabilitato l'utilizzo di **DataView** per eliminare righe e viene aggiunta una nuova riga alla tabella sottostante utilizzando il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="92481-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92481-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92481-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="92481-127">DataView</span><span class="sxs-lookup"><span data-stu-id="92481-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="92481-128">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="92481-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
