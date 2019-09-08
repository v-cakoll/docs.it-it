---
title: Eliminazione di DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 3f48339539f08bbc1c2c15035741375bd9ade553
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784718"
---
# <a name="datarow-deletion"></a><span data-ttu-id="ad011-102">Eliminazione di DataRow</span><span class="sxs-lookup"><span data-stu-id="ad011-102">DataRow Deletion</span></span>
<span data-ttu-id="ad011-103">Esistono due metodi che è possibile utilizzare per eliminare un <xref:System.Data.DataRow> oggetto da un <xref:System.Data.DataTable> oggetto: <xref:System.Data.DataRowCollection> il metodo **Remove** dell'oggetto e il <xref:System.Data.DataRow.Delete%2A> metodo dell'oggetto **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="ad011-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="ad011-104">Mentre il <xref:System.Data.DataRowCollection.Remove%2A> metodo elimina un **DataRow** da **DataRowCollection**, il <xref:System.Data.DataRow.Delete%2A> metodo contrassegna solo la riga per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="ad011-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="ad011-105">La rimozione effettiva si verifica quando l'applicazione chiama il metodo **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="ad011-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="ad011-106">L'utilizzo di <xref:System.Data.DataRow.Delete%2A> consente di verificare a livello di programmazione le righe contrassegnate per l'eliminazione prima che vengano eliminate effettivamente.</span><span class="sxs-lookup"><span data-stu-id="ad011-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="ad011-107">Quando una riga è contrassegnata per l'eliminazione, la relativa proprietà <xref:System.Data.DataRow.RowState%2A> è impostata su <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad011-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="ad011-108"><xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non devono essere chiamato in un ciclo foreach durante l'iterazione tramite un oggetto <xref:System.Data.DataRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="ad011-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="ad011-109"><xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non modificano lo stato della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ad011-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="ad011-110">Quando si usa <xref:System.Data.DataSet> un **oggetto o DataTable** insieme a **un DataAdapter** e a un'origine dati relazionale, usare il metodo **Delete** del **DataRow** per rimuovere la riga.</span><span class="sxs-lookup"><span data-stu-id="ad011-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="ad011-111">Il metodo **Delete** contrassegna la riga come **eliminata** nel **DataSet** o **DataTable** , ma non la rimuove.</span><span class="sxs-lookup"><span data-stu-id="ad011-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="ad011-112">Al contrario, quando **DataAdapter** rileva una riga contrassegnata come **eliminata**, viene eseguito il metodo **DeleteCommand** per eliminare la riga nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ad011-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="ad011-113">La riga può quindi essere rimossa definitivamente usando il metodo **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="ad011-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="ad011-114">Se si utilizza **Rimuovi** per eliminare la riga, la riga viene rimossa interamente dalla tabella, ma l'oggetto **DataAdapter** non eliminerà la riga nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="ad011-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="ad011-115">Il metodo **Remove** di **DataRowCollection** accetta un **DataRow** come argomento e lo rimuove dalla raccolta, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ad011-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="ad011-116">Al contrario, nell'esempio seguente viene illustrato come chiamare il metodo **Delete** su un **DataRow** per modificare il valore di **RowState** in **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="ad011-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="ad011-117">Se una riga è contrassegnata per l'eliminazione e si chiama il metodo **AcceptChanges** dell'oggetto **DataTable** , la riga viene rimossa dalla **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ad011-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="ad011-118">Al contrario, se si chiama **RejectChanges**, il **RowState** della riga ritorna a quello che era prima che venisse contrassegnato come **eliminato**.</span><span class="sxs-lookup"><span data-stu-id="ad011-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad011-119">Se viene **aggiunto il valore** **RowState** di un **DataRow** , ovvero è stato appena aggiunto alla tabella e viene quindi contrassegnato come **eliminato**, viene rimosso dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="ad011-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad011-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad011-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ad011-121">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="ad011-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ad011-122">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad011-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
