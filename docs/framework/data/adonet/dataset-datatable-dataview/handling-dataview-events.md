---
title: Gestione di eventi DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 9e67aef2a39a04adfdcc036c008aa80c9151c14b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762559"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="d9b54-102">Gestione di eventi DataView</span><span class="sxs-lookup"><span data-stu-id="d9b54-102">Handling DataView Events</span></span>
<span data-ttu-id="d9b54-103">Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="d9b54-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="d9b54-104">Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio.</span><span class="sxs-lookup"><span data-stu-id="d9b54-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="d9b54-105">Il **ListChanged** evento invierà una notifica se l'elenco delle righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di una nuova sequenza di ordinamento o un filtro.</span><span class="sxs-lookup"><span data-stu-id="d9b54-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="d9b54-106">Il **ListChanged** evento implementa il **ListChangedEventHandler** delegare del <xref:System.ComponentModel> dello spazio dei nomi e accetta come input un <xref:System.ComponentModel.ListChangedEventArgs> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9b54-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="d9b54-107">È possibile determinare il tipo di modifica utilizzando il <xref:System.ComponentModel.ListChangedType> valore di enumerazione nel **ListChangedType** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9b54-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="d9b54-108">Per le modifiche che implicano l'aggiunta, eliminazione o spostamento di righe, il nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata accessibili tramite il **NewIndex** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9b54-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="d9b54-109">Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando il **OldIndex** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9b54-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="d9b54-110">Il **DataViewManager** espone inoltre un **ListChanged** evento per notificare se una tabella è stato aggiunta o rimossa o se è stata apportata una modifica per il **relazioni** insieme del sottostante **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="d9b54-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="d9b54-111">Esempio di codice seguente viene illustrato come aggiungere un **ListChanged** gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d9b54-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9b54-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9b54-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="d9b54-113">DataView</span><span class="sxs-lookup"><span data-stu-id="d9b54-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="d9b54-114">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d9b54-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
