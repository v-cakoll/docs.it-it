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
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c19e78ca05b339898a27a1e5f98412224586aae9
ms.sourcegitcommit: c3ebb11a66e85a465c9ba2c42592222630b7ff9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a><span data-ttu-id="29c15-102">Procedura: Aggiungere e rimuovere singoli elementi di un oggetto BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="29c15-102">How to: Add and Take Items Individually from a BlockingCollection</span></span>
<span data-ttu-id="29c15-103">Questo esempio mostra come aggiungere e rimuovere elementi in un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> in modo bloccante e non bloccante.</span><span class="sxs-lookup"><span data-stu-id="29c15-103">This example shows how to add and remove items from a <xref:System.Collections.Concurrent.BlockingCollection%601> in both a blocking and a non-blocking manner.</span></span> <span data-ttu-id="29c15-104">Per altre informazioni su <xref:System.Collections.Concurrent.BlockingCollection%601>, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="29c15-104">For more information on <xref:System.Collections.Concurrent.BlockingCollection%601>, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
 <span data-ttu-id="29c15-105">Per un esempio su come enumerare un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> finché non sarà vuoto e non verranno aggiunti altri elementi, vedere [Procedura: Usare ForEach per rimuovere elementi in un oggetto BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).</span><span class="sxs-lookup"><span data-stu-id="29c15-105">For an example of how to enumerate a <xref:System.Collections.Concurrent.BlockingCollection%601> until it is empty and no more elements will be added, see [How to: Use ForEach to Remove Items in a BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="29c15-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="29c15-106">Example</span></span>  
 <span data-ttu-id="29c15-107">Il primo esempio mostra come aggiungere e rimuovere elementi in modo da bloccare le operazioni se la raccolta è temporaneamente vuota (durante la rimozione) o ha raggiunto la capacità massima (durante l'aggiunta) oppure se è trascorso un periodo di timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="29c15-107">This first example shows how to add and take items so that the operations will block if the collection is either temporarily empty (when taking) or at maximum capacity (when adding), or if a specified timeout period has elapsed.</span></span> <span data-ttu-id="29c15-108">Si noti che il blocco relativo alla capacità massima è abilitato solo quando l'oggetto BlockingCollection è stato creato specificando una capacità massima nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="29c15-108">Note that blocking on maximum capacity is only enabled when the BlockingCollection has been created with a maximum capacity specified in the constructor.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="29c15-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="29c15-109">Example</span></span>  
 <span data-ttu-id="29c15-110">Questo secondo esempio mostra come aggiungere e rimuovere elementi in modo da non bloccare le operazioni.</span><span class="sxs-lookup"><span data-stu-id="29c15-110">This second example shows how to add and take items so that the operations will not block.</span></span> <span data-ttu-id="29c15-111">Se non è presente alcun elemento, se è stata raggiunta la capacità massima per una raccolta con vincoli oppure è trascorso il periodo di timeout, l'operazione <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> restituisce false.</span><span class="sxs-lookup"><span data-stu-id="29c15-111">If no item is present, maximum capacity on a bounded collection has been reached, or the timeout period has elapsed, then the <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> or <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> operation returns false.</span></span> <span data-ttu-id="29c15-112">In questo modo, il thread può eseguire per un breve periodo altre operazioni utili e quindi riprovare a recuperare un nuovo elemento o ad aggiungere lo stesso elemento che non è stato possibile aggiungere in precedenza.</span><span class="sxs-lookup"><span data-stu-id="29c15-112">This allows the thread to do some other useful work for a while and then try again later to either retrieve a new item, or try to add the same item that could not be added previously.</span></span> <span data-ttu-id="29c15-113">Il programma illustra inoltre come implementare l'annullamento quando si accede a un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="29c15-113">The program also demonstrates how to implement cancellation when accessing a <xref:System.Collections.Concurrent.BlockingCollection%601>.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="29c15-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29c15-114">See Also</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [<span data-ttu-id="29c15-115">Panoramica di BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="29c15-115">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)
