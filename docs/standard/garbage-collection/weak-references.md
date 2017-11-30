---
title: Riferimenti deboli
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a><span data-ttu-id="7f70e-102">Riferimenti deboli</span><span class="sxs-lookup"><span data-stu-id="7f70e-102">Weak References</span></span>
<span data-ttu-id="7f70e-103">Il Garbage Collector non può raccogliere un oggetto usato da un'applicazione finché il codice dell'applicazione è in grado raggiungere tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="7f70e-103">The garbage collector cannot collect an object in use by an application while the application's code can reach that object.</span></span> <span data-ttu-id="7f70e-104">Si dice che l'applicazione ha un riferimento sicuro all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7f70e-104">The application is said to have a strong reference to the object.</span></span>  
  
 <span data-ttu-id="7f70e-105">Un riferimento debole consente al Garbage Collector di raccogliere l'oggetto, pur senza impedire all'applicazione di accedervi.</span><span class="sxs-lookup"><span data-stu-id="7f70e-105">A weak reference permits the garbage collector to collect the object while still allowing the application to access the object.</span></span> <span data-ttu-id="7f70e-106">Un riferimento debole è valido solo durante il periodo di tempo indeterminato fino a quando l'oggetto viene raccolto, se non è presente nessun riferimento sicuro.</span><span class="sxs-lookup"><span data-stu-id="7f70e-106">A weak reference is valid only during the indeterminate amount of time until the object is collected when no strong references exist.</span></span> <span data-ttu-id="7f70e-107">Quando si usa un riferimento debole, l'applicazione può comunque ottenere un riferimento sicuro all'oggetto, che ne impedirà la raccolta.</span><span class="sxs-lookup"><span data-stu-id="7f70e-107">When you use a weak reference, the application can still obtain a strong reference to the object, which prevents it from being collected.</span></span> <span data-ttu-id="7f70e-108">Tuttavia esiste sempre il rischio che il Garbage Collector raggiunga l'oggetto prima che venga ristabilito un riferimento sicuro.</span><span class="sxs-lookup"><span data-stu-id="7f70e-108">However, there is always the risk that the garbage collector will get to the object first before a strong reference is reestablished.</span></span>  
  
 <span data-ttu-id="7f70e-109">I riferimenti deboli sono utili per gli oggetti che usano grandi quantità di memoria ma possono essere ricreati facilmente se vengono raccolti dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f70e-109">Weak references are useful for objects that use a lot of memory, but can be recreated easily if they are reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="7f70e-110">Si supponga che una visualizzazione albero in un'applicazione Windows Form visualizza una scelta complessa gerarchica delle opzioni all'utente.</span><span class="sxs-lookup"><span data-stu-id="7f70e-110">Suppose a tree view in a Windows Forms application displays a complex hierarchical choice of options to the user.</span></span> <span data-ttu-id="7f70e-111">Se i dati sottostanti sono di grandi dimensioni, non è efficiente mantenere la struttura in memoria mentre l'utente esegue altre operazioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f70e-111">If the underlying data is large, keeping the tree in memory is inefficient when the user is involved with something else in the application.</span></span>  
  
 <span data-ttu-id="7f70e-112">Quando l'utente passa a un'altra parte dell'applicazione, è possibile utilizzare la <xref:System.WeakReference> classe per creare un riferimento debole all'albero e distruggere tutti i riferimenti forti.</span><span class="sxs-lookup"><span data-stu-id="7f70e-112">When the user switches away to another part of the application, you can use the <xref:System.WeakReference> class to create a weak reference to the tree and destroy all strong references.</span></span> <span data-ttu-id="7f70e-113">Quando l'utente torna alla struttura, l'applicazione cerca di ottenere un riferimento sicuro alla struttura ad albero e, se vi riesce, evita la ricostruzione della struttura.</span><span class="sxs-lookup"><span data-stu-id="7f70e-113">When the user switches back to the tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.</span></span>  
  
 <span data-ttu-id="7f70e-114">Per stabilire un riferimento debole a un oggetto, è necessario creare un <xref:System.WeakReference> utilizzando l'istanza dell'oggetto da rilevare.</span><span class="sxs-lookup"><span data-stu-id="7f70e-114">To establish a weak reference with an object, you create a <xref:System.WeakReference> using the instance of the object to be tracked.</span></span> <span data-ttu-id="7f70e-115">È quindi necessario impostare la proprietà <xref:System.WeakReference.Target%2A> su questo oggetto e impostare il riferimento originale all'oggetto su `null`.</span><span class="sxs-lookup"><span data-stu-id="7f70e-115">You then set the <xref:System.WeakReference.Target%2A> property to that object and set the original reference to the object to `null`.</span></span> <span data-ttu-id="7f70e-116">Per un esempio di codice, vedere <xref:System.WeakReference> nella libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="7f70e-116">For a code example, see <xref:System.WeakReference> in the class library.</span></span>  
  
## <a name="short-and-long-weak-references"></a><span data-ttu-id="7f70e-117">Riferimenti deboli brevi e lunghi</span><span class="sxs-lookup"><span data-stu-id="7f70e-117">Short and Long Weak References</span></span>  
 <span data-ttu-id="7f70e-118">È possibile creare un riferimento debole breve o lungo:</span><span class="sxs-lookup"><span data-stu-id="7f70e-118">You can create a short weak reference or a long weak reference:</span></span>  
  
-   <span data-ttu-id="7f70e-119">Short</span><span class="sxs-lookup"><span data-stu-id="7f70e-119">Short</span></span>  
  
     <span data-ttu-id="7f70e-120">La destinazione di un riferimento debole breve diventa `null` quando l'oggetto viene raccolto dall'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f70e-120">The target of a short weak reference becomes `null` when the object is reclaimed by garbage collection.</span></span> <span data-ttu-id="7f70e-121">Il riferimento debole è in sé un oggetto gestito ed è soggetto a Garbage Collection come qualsiasi altro oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="7f70e-121">The weak reference is itself a managed object, and is subject to garbage collection just like any other managed object.</span></span>  <span data-ttu-id="7f70e-122">Un riferimento debole breve è il costruttore predefinito per <xref:System.WeakReference>.</span><span class="sxs-lookup"><span data-stu-id="7f70e-122">A short weak reference is the default constructor for <xref:System.WeakReference>.</span></span>  
  
-   <span data-ttu-id="7f70e-123">Long</span><span class="sxs-lookup"><span data-stu-id="7f70e-123">Long</span></span>  
  
     <span data-ttu-id="7f70e-124">Un riferimento debole lungo viene mantenuto dopo l'oggetto <xref:System.Object.Finalize%2A> metodo è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7f70e-124">A long weak reference is retained after the object's <xref:System.Object.Finalize%2A> method has been called.</span></span> <span data-ttu-id="7f70e-125">Ciò consente che l'oggetto venga ricreato, ma lo stato dell'oggetto non è prevedibile.</span><span class="sxs-lookup"><span data-stu-id="7f70e-125">This allows the object to be recreated, but the state of the object remains unpredictable.</span></span> <span data-ttu-id="7f70e-126">Per utilizzare un riferimento lungo, specificare `true` nel <xref:System.WeakReference> costruttore.</span><span class="sxs-lookup"><span data-stu-id="7f70e-126">To use a long reference, specify `true` in the <xref:System.WeakReference> constructor.</span></span>  
  
     <span data-ttu-id="7f70e-127">Se il tipo di oggetto non ha un <xref:System.Object.Finalize%2A> (metodo), il riferimento debole breve funzionalità si applica e il riferimento debole è valido solo fino a quando non verrà raccolti la destinazione, che può verificarsi in qualsiasi momento dopo il finalizzatore viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="7f70e-127">If the object's type does not have a <xref:System.Object.Finalize%2A> method, the short weak reference functionality applies and the weak reference is valid only until the target is collected, which can occur anytime after the finalizer is run.</span></span>  
  
 <span data-ttu-id="7f70e-128">Per stabilire un riferimento forte e utilizzare nuovamente l'oggetto, eseguire il cast di <xref:System.WeakReference.Target%2A> proprietà di un <xref:System.WeakReference> per il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7f70e-128">To establish a strong reference and use the object again, cast the <xref:System.WeakReference.Target%2A> property of a <xref:System.WeakReference> to the type of the object.</span></span> <span data-ttu-id="7f70e-129">Se il <xref:System.WeakReference.Target%2A> restituisce proprietà `null`, l'oggetto è stato raccolto; in caso contrario, è possibile continuare a utilizzare l'oggetto perché l'applicazione ha recuperato un riferimento forte ad esso.</span><span class="sxs-lookup"><span data-stu-id="7f70e-129">If the <xref:System.WeakReference.Target%2A> property returns `null`, the object was collected; otherwise, you can continue to use the object because the application has regained a strong reference to it.</span></span>  
  
## <a name="guidelines-for-using-weak-references"></a><span data-ttu-id="7f70e-130">Linee guida per l'uso dei riferimenti deboli</span><span class="sxs-lookup"><span data-stu-id="7f70e-130">Guidelines for Using Weak References</span></span>  
 <span data-ttu-id="7f70e-131">Usare i riferimenti deboli lunghi solo in caso di necessità, perché dopo la finalizzazione lo stato dell'oggetto è imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="7f70e-131">Use long weak references only when necessary as the state of the object is unpredictable after finalization.</span></span>  
  
 <span data-ttu-id="7f70e-132">Evitare di usare riferimenti deboli a oggetti di piccole dimensioni, poiché il puntatore può avere dimensioni equivalenti o superiori.</span><span class="sxs-lookup"><span data-stu-id="7f70e-132">Avoid using weak references to small objects because the pointer itself may be as large or larger.</span></span>  
  
 <span data-ttu-id="7f70e-133">Evitare di usare i riferimenti deboli come soluzione automatica per i problemi di gestione della memoria.</span><span class="sxs-lookup"><span data-stu-id="7f70e-133">Avoid using weak references as an automatic solution to memory management problems.</span></span> <span data-ttu-id="7f70e-134">In alternativa, sviluppare un criterio di memorizzazione nella cache efficiente per gestire gli oggetti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f70e-134">Instead, develop an effective caching policy for handling your application's objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f70e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f70e-135">See Also</span></span>  
 [<span data-ttu-id="7f70e-136">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="7f70e-136">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
