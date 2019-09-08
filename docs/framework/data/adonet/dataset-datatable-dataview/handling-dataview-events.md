---
title: Gestione di eventi DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: c36c68b0375e7d03aac36de7d02b2c9579ea9316
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784596"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="4a5f3-102">Gestione di eventi DataView</span><span class="sxs-lookup"><span data-stu-id="4a5f3-102">Handling DataView Events</span></span>
<span data-ttu-id="4a5f3-103">Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="4a5f3-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="4a5f3-104">Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio.</span><span class="sxs-lookup"><span data-stu-id="4a5f3-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="4a5f3-105">L'evento **ListChanged** invia inoltre una notifica all'utente se l'elenco di righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di un nuovo ordinamento o di un filtro.</span><span class="sxs-lookup"><span data-stu-id="4a5f3-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="4a5f3-106">L'evento **ListChanged** implementa il <xref:System.ComponentModel> delegato ListChangedEventHandler dello spazio dei nomi e accetta come input <xref:System.ComponentModel.ListChangedEventArgs> un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4a5f3-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="4a5f3-107">È possibile determinare il tipo di modifica che si è verificata usando il <xref:System.ComponentModel.ListChangedType> valore di enumerazione nella proprietà **ListChangedType** dell'oggetto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="4a5f3-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="4a5f3-108">Per le modifiche che comportano l'aggiunta, l'eliminazione o lo spostamento di righe, è possibile accedere al nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata utilizzando la proprietà **newIndex** dell'oggetto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="4a5f3-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="4a5f3-109">Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando la proprietà **OldIndex** dell'oggetto **ListChangedEventArgs** .</span><span class="sxs-lookup"><span data-stu-id="4a5f3-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="4a5f3-110">**DataViewManager** espone inoltre un evento **ListChanged** per notificare all'utente se una tabella è stata aggiunta o rimossa o se è stata apportata una modifica alla raccolta **Relations** del **set di dati**sottostante.</span><span class="sxs-lookup"><span data-stu-id="4a5f3-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="4a5f3-111">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un gestore eventi **ListChanged** .</span><span class="sxs-lookup"><span data-stu-id="4a5f3-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a5f3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a5f3-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="4a5f3-113">DataView</span><span class="sxs-lookup"><span data-stu-id="4a5f3-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="4a5f3-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a5f3-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
