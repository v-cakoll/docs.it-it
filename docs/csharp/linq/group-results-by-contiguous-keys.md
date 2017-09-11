---
title: Raggruppare i risultati per chiavi contigue
description: Come raggruppare i risultati per chiavi contigue.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ddd028a3aad5186ef6773b32e9f9e8e1cbff95fc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="44ba0-104">Raggruppare i risultati per chiavi contigue</span><span class="sxs-lookup"><span data-stu-id="44ba0-104">Group results by contiguous keys</span></span>

<span data-ttu-id="44ba0-105">Nell'esempio seguente viene illustrato come raggruppare elementi in blocchi che rappresentano sottosequenze di chiavi contigue.</span><span class="sxs-lookup"><span data-stu-id="44ba0-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="44ba0-106">Si supponga di avere ad esempio la sequenza di coppie chiave-valore riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="44ba0-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="44ba0-107">Chiave</span><span class="sxs-lookup"><span data-stu-id="44ba0-107">Key</span></span>|<span data-ttu-id="44ba0-108">Valore</span><span class="sxs-lookup"><span data-stu-id="44ba0-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="44ba0-109">A</span><span class="sxs-lookup"><span data-stu-id="44ba0-109">A</span></span>|<span data-ttu-id="44ba0-110">Me</span><span class="sxs-lookup"><span data-stu-id="44ba0-110">We</span></span>|  
|<span data-ttu-id="44ba0-111">A</span><span class="sxs-lookup"><span data-stu-id="44ba0-111">A</span></span>|<span data-ttu-id="44ba0-112">think</span><span class="sxs-lookup"><span data-stu-id="44ba0-112">think</span></span>|  
|<span data-ttu-id="44ba0-113">A</span><span class="sxs-lookup"><span data-stu-id="44ba0-113">A</span></span>|<span data-ttu-id="44ba0-114">that</span><span class="sxs-lookup"><span data-stu-id="44ba0-114">that</span></span>|  
|<span data-ttu-id="44ba0-115">B</span><span class="sxs-lookup"><span data-stu-id="44ba0-115">B</span></span>|<span data-ttu-id="44ba0-116">Linq</span><span class="sxs-lookup"><span data-stu-id="44ba0-116">Linq</span></span>|  
|<span data-ttu-id="44ba0-117">C</span><span class="sxs-lookup"><span data-stu-id="44ba0-117">C</span></span>|<span data-ttu-id="44ba0-118">is</span><span class="sxs-lookup"><span data-stu-id="44ba0-118">is</span></span>|  
|<span data-ttu-id="44ba0-119">A</span><span class="sxs-lookup"><span data-stu-id="44ba0-119">A</span></span>|<span data-ttu-id="44ba0-120">really</span><span class="sxs-lookup"><span data-stu-id="44ba0-120">really</span></span>|  
|<span data-ttu-id="44ba0-121">B</span><span class="sxs-lookup"><span data-stu-id="44ba0-121">B</span></span>|<span data-ttu-id="44ba0-122">cool</span><span class="sxs-lookup"><span data-stu-id="44ba0-122">cool</span></span>|  
|<span data-ttu-id="44ba0-123">B</span><span class="sxs-lookup"><span data-stu-id="44ba0-123">B</span></span>|<span data-ttu-id="44ba0-124">!</span><span class="sxs-lookup"><span data-stu-id="44ba0-124">!</span></span>|  
  
 <span data-ttu-id="44ba0-125">Verranno creati i gruppi seguenti in questo ordine:</span><span class="sxs-lookup"><span data-stu-id="44ba0-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="44ba0-126">We, think, that</span><span class="sxs-lookup"><span data-stu-id="44ba0-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="44ba0-127">Linq</span><span class="sxs-lookup"><span data-stu-id="44ba0-127">Linq</span></span>  
  
3.  <span data-ttu-id="44ba0-128">is</span><span class="sxs-lookup"><span data-stu-id="44ba0-128">is</span></span>  
  
4.  <span data-ttu-id="44ba0-129">really</span><span class="sxs-lookup"><span data-stu-id="44ba0-129">really</span></span>  
  
5.  <span data-ttu-id="44ba0-130">cool, !</span><span class="sxs-lookup"><span data-stu-id="44ba0-130">cool, !</span></span>  
  
 <span data-ttu-id="44ba0-131">La soluzione viene implementata come metodo di estensione thread-safe che restituisce i risultati in modalità di flusso.</span><span class="sxs-lookup"><span data-stu-id="44ba0-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="44ba0-132">In altre parole, i gruppi vengono prodotti man mano che ci si sposta lungo la sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="44ba0-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="44ba0-133">A differenza degli operatori `group` o `orderby`, questa soluzione può iniziare a restituire i gruppi al chiamante prima che sia stata letta tutta la sequenza.</span><span class="sxs-lookup"><span data-stu-id="44ba0-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="44ba0-134">La caratteristica thread-safe viene ottenuta effettuando una copia di ogni gruppo o blocco nel corso dell'iterazione della sequenza di origine, come spiegato nei commenti del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="44ba0-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="44ba0-135">Se la sequenza di origine include una sequenza di grandi dimensioni di elementi contigui, Common Language Runtime potrebbe generare un'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="44ba0-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44ba0-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="44ba0-136">Example</span></span>  
 <span data-ttu-id="44ba0-137">Nell'esempio seguente viene illustrato sia il metodo di estensione che il codice client usato.</span><span class="sxs-lookup"><span data-stu-id="44ba0-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 <span data-ttu-id="44ba0-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="44ba0-138">[!code-cs[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]</span></span>  
  
 <span data-ttu-id="44ba0-139">Per usare il metodo di estensione nel progetto, copiare la classe statica `MyExtensions` in un file di codice sorgente nuovo o esistente e, se richiesto, aggiungere una direttiva `using` per lo spazio dei nomi in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="44ba0-139">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ba0-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44ba0-140">See also</span></span>  
 [<span data-ttu-id="44ba0-141">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="44ba0-141">LINQ Query Expressions</span></span>](index.md)   
 

