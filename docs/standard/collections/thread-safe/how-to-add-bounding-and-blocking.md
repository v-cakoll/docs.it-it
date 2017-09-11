---
title: "Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3258534cb0bf67b180080eca4f7cefc65c609fa4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="916cd-102">Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta</span><span class="sxs-lookup"><span data-stu-id="916cd-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="916cd-103">Questo esempio illustra come aggiungere la funzionalità di delimitazione e blocco a una classe di raccolta personalizzata implementando l'interfaccia <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> nella classe e successivamente usando un'istanza della classe come meccanismo di archiviazione interno per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="916cd-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.</span></span> <span data-ttu-id="916cd-104">Per altre informazioni su delimitazione e blocco, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="916cd-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="916cd-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="916cd-105">Example</span></span>  
 <span data-ttu-id="916cd-106">La classe di raccolta personalizzata è una coda di priorità di base in cui i livelli di priorità sono rappresentati come matrice di oggetti <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="916cd-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> objects.</span></span> <span data-ttu-id="916cd-107">Nessun ordinamento aggiuntivo viene eseguito all'interno di ogni coda.</span><span class="sxs-lookup"><span data-stu-id="916cd-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="916cd-108">Nel codice client vengono avviate tre attività.</span><span class="sxs-lookup"><span data-stu-id="916cd-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="916cd-109">La prima attività esegue il polling per le sequenze di tasti che abilitano l'annullamento in qualsiasi momento durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="916cd-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="916cd-110">La seconda attività è il thread producer. Aggiunge nuovi elementi alla raccolta di blocco e assegna a ogni elemento una priorità basata su un valore casuale.</span><span class="sxs-lookup"><span data-stu-id="916cd-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="916cd-111">La terza attività rimuove gli elementi dalla raccolta appena diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="916cd-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="916cd-112">È possibile modificare il comportamento dell'applicazione rendendo uno dei thread più veloce rispetto all'altro.</span><span class="sxs-lookup"><span data-stu-id="916cd-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="916cd-113">Se il producer viene eseguito più velocemente, si noterà la funzionalità di delimitazione perché la raccolta di blocco impedisce l'aggiunta di elementi se contiene già il numero di elementi specificato nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="916cd-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="916cd-114">Se il consumer viene eseguito più velocemente, si noterà la funzionalità di blocco perché il consumer aspetta che un nuovo elemento venga aggiunto.</span><span class="sxs-lookup"><span data-stu-id="916cd-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 <span data-ttu-id="916cd-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span><span class="sxs-lookup"><span data-stu-id="916cd-115">[!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]</span></span>  
  
 <span data-ttu-id="916cd-116">Per impostazione predefinita, l'archiviazione per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> è <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="916cd-116">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916cd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="916cd-117">See Also</span></span>  
 [<span data-ttu-id="916cd-118">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="916cd-118">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)

