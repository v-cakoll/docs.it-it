---
title: Eliminazione di DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 57f51ada00bf24617ca3e295a010aae64f0aa849
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196138"
---
# <a name="datarow-deletion"></a><span data-ttu-id="6bb14-102">Eliminazione di DataRow</span><span class="sxs-lookup"><span data-stu-id="6bb14-102">DataRow Deletion</span></span>
<span data-ttu-id="6bb14-103">Sono disponibili due metodi è possibile usare per eliminare un <xref:System.Data.DataRow> dell'oggetto da un <xref:System.Data.DataTable> oggetto: il **rimuovere** metodo del <xref:System.Data.DataRowCollection> oggetto e il <xref:System.Data.DataRow.Delete%2A> metodo del **DataRow**oggetto.</span><span class="sxs-lookup"><span data-stu-id="6bb14-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="6bb14-104">Mentre il <xref:System.Data.DataRowCollection.Remove%2A> eliminazioni metodo una **DataRow** dal **DataRowCollection**, il <xref:System.Data.DataRow.Delete%2A> metodo contrassegna solo la riga per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="6bb14-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="6bb14-105">La rimozione effettiva si verifica quando l'applicazione chiama il **AcceptChanges** (metodo).</span><span class="sxs-lookup"><span data-stu-id="6bb14-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="6bb14-106">L'utilizzo di <xref:System.Data.DataRow.Delete%2A> consente di verificare a livello di programmazione le righe contrassegnate per l'eliminazione prima che vengano eliminate effettivamente.</span><span class="sxs-lookup"><span data-stu-id="6bb14-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="6bb14-107">Quando una riga è contrassegnata per l'eliminazione, la relativa proprietà <xref:System.Data.DataRow.RowState%2A> è impostata su <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="6bb14-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="6bb14-108"><xref:System.Data.DataRow.Delete%2A> e <xref:System.Data.DataRowCollection.Remove%2A> non devono essere chiamato in un ciclo foreach durante l'iterazione tramite un oggetto <xref:System.Data.DataRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="6bb14-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <xref:System.Data.DataRow.Delete%2A> <span data-ttu-id="6bb14-109">né <xref:System.Data.DataRowCollection.Remove%2A> modificano lo stato della raccolta.</span><span class="sxs-lookup"><span data-stu-id="6bb14-109">nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="6bb14-110">Quando si usa una <xref:System.Data.DataSet> o **DataTable** in combinazione con un **DataAdapter** e un'origine dati relazionale, usare il **eliminare** metodo il  **DataRow** per rimuovere la riga.</span><span class="sxs-lookup"><span data-stu-id="6bb14-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="6bb14-111">Il **eliminare** metodo contrassegna la riga come **Deleted** nel **set di dati** oppure **DataTable** ma non lo rimuove.</span><span class="sxs-lookup"><span data-stu-id="6bb14-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="6bb14-112">Invece, quando la **DataAdapter** rileva una riga contrassegnata come **Deleted**, esegue relativo **DeleteCommand** metodo per eliminare la riga nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6bb14-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="6bb14-113">La riga può quindi essere rimosso definitivamente usando il **AcceptChanges** (metodo).</span><span class="sxs-lookup"><span data-stu-id="6bb14-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="6bb14-114">Se si usa **rimuovere** per eliminare la riga, la riga viene rimossa completamente dalla tabella, ma la **DataAdapter** non eliminerà la riga nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6bb14-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="6bb14-115">Il **rimuovere** metodo per il **DataRowCollection** accetta una **DataRow** come argomento e lo rimuove dalla raccolta, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6bb14-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="6bb14-116">Al contrario, l'esempio seguente viene illustrato come chiamare il **eliminare** metodo su un **DataRow** modificare relativo **RowState** a **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="6bb14-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="6bb14-117">Se una riga è contrassegnata per l'eliminazione e si chiama il **AcceptChanges** metodo per il **DataTable** dell'oggetto, la riga viene rimossa dal **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="6bb14-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="6bb14-118">Al contrario, se si chiama **RejectChanges**, il **RowState** Ripristina la riga si trovava prima di essere contrassegnato come **Deleted**.</span><span class="sxs-lookup"><span data-stu-id="6bb14-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bb14-119">Se il **RowState** di un **DataRow** viene **Added**, vale a dire è stato aggiunto solo alla tabella e viene quindi contrassegnato come **Deleted**, è rimosso dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="6bb14-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb14-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bb14-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="6bb14-121">Manipolazione di dati in un oggetto DataTable</span><span class="sxs-lookup"><span data-stu-id="6bb14-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="6bb14-122">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="6bb14-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
