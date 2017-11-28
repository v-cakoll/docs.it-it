---
title: 'Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b365d6d3236919f65c840343ec3b33edebea758b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="3763e-102">Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="3763e-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="3763e-103">Questo esempio mostra come aggiungere e rimuovere elementi da un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> bloccando e non bloccando le operazioni.</span><span class="sxs-lookup"><span data-stu-id="3763e-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and non-blocking manner.</span></span> <span data-ttu-id="3763e-104">Per altre informazioni su <xref:System.Collections.Concurrent.BlockingCollection%601>, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3763e-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="3763e-105">Per un esempio di come enumerare un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> finché non è vuoto e non vengono aggiunti altri elementi, vedere [Procedura: Usare ForEach per rimuovere elementi in un oggetto BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)</span><span class="sxs-lookup"><span data-stu-id="3763e-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="3763e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="3763e-106">Example</span></span>  
 <span data-ttu-id="3763e-107">Il primo esempio mostra come aggiungere e rimuovere elementi in modo che da bloccare le operazioni se la raccolta è temporaneamente vuota (durante la rimozione), ha raggiunto la capacità massima (durante l'aggiunta) oppure quando è trascorso un periodo di timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="3763e-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or a specified timeout period has elapsed.</span></span> <span data-ttu-id="3763e-108">Si noti che il blocco relativo alla capacità massima è abilitato solo quando l'oggetto BlockingCollection è stato creato specificando una capacità massima nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="3763e-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="3763e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3763e-109">Example</span></span>  
 <span data-ttu-id="3763e-110">Questo secondo esempio mostra come aggiungere e rimuovere elementi in modo da non bloccare le operazioni.</span><span class="sxs-lookup"><span data-stu-id="3763e-110">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="3763e-111">Se non è presente alcun elemento, se è stata raggiunta la capacità massima per una raccolta limitata oppure se è trascorso il periodo di timeout, l'operazione <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> restituisce false.</span><span class="sxs-lookup"><span data-stu-id="3763e-111">If no item is present, or maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="3763e-112">In questo modo si consente al thread di eseguire per un breve periodo altre operazioni utili e quindi, in un secondo momento, provare a recuperare il nuovo elemento o ad aggiungere lo stesso elemento che non è stato possibile aggiungere in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3763e-112">This allows the thread to do some other useful work for awhile and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="3763e-113">Il programma dimostra anche come implementare l'annullamento quando si accede a un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="3763e-113">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="3763e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3763e-114">See Also</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [<span data-ttu-id="3763e-115">Panoramica di BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="3763e-115">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
