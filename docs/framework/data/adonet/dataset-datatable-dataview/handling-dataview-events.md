---
title: Gestione di eventi DataView
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
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf3b02227de5068a031cedb73269148c7d5262a0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="handling-dataview-events"></a><span data-ttu-id="48387-102">Gestione di eventi DataView</span><span class="sxs-lookup"><span data-stu-id="48387-102">Handling DataView Events</span></span>
<span data-ttu-id="48387-103">Per determinare se una visualizzazione è stata aggiornata, è possibile usare l'evento <xref:System.Data.DataView.ListChanged> del <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="48387-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="48387-104">Gli aggiornamenti che generano l'evento includono l'aggiunta, l'eliminazione o la modifica di una riga nella tabella sottostante; l'aggiunta o l'eliminazione di una colonna nello schema della tabella sottostante e una modifica in una relazione padre o figlio.</span><span class="sxs-lookup"><span data-stu-id="48387-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="48387-105">Il **ListChanged** evento invierà una notifica se l'elenco delle righe visualizzato è stato modificato in modo significativo a causa dell'applicazione di una nuova sequenza di ordinamento o un filtro.</span><span class="sxs-lookup"><span data-stu-id="48387-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="48387-106">Il **ListChanged** evento implementa il **ListChangedEventHandler** delegare del <xref:System.ComponentModel> dello spazio dei nomi e accetta come input un <xref:System.ComponentModel.ListChangedEventArgs> oggetto.</span><span class="sxs-lookup"><span data-stu-id="48387-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="48387-107">È possibile determinare il tipo di modifica utilizzando il <xref:System.ComponentModel.ListChangedType> valore di enumerazione nel **ListChangedType** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="48387-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="48387-108">Per le modifiche che implicano l'aggiunta, eliminazione o spostamento di righe, il nuovo indice della riga aggiunta o spostata e all'indice precedente della riga eliminata accessibili tramite il **NewIndex** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="48387-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="48387-109">Nel caso di una riga spostata, è possibile accedere all'indice precedente della riga spostata utilizzando il **OldIndex** proprietà del **ListChangedEventArgs** oggetto.</span><span class="sxs-lookup"><span data-stu-id="48387-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="48387-110">Il **DataViewManager** espone inoltre un **ListChanged** evento per notificare se una tabella è stato aggiunta o rimossa o se è stata apportata una modifica per il **relazioni** insieme del sottostante **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="48387-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="48387-111">Esempio di codice seguente viene illustrato come aggiungere un **ListChanged** gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="48387-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48387-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48387-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="48387-113">DataView</span><span class="sxs-lookup"><span data-stu-id="48387-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="48387-114">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="48387-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
