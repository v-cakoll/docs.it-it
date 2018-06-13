---
title: Raggruppare i risultati per chiavi contigue
description: Come raggruppare i risultati per chiavi contigue.
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281437"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="d7eb8-103">Raggruppare i risultati per chiavi contigue</span><span class="sxs-lookup"><span data-stu-id="d7eb8-103">Group results by contiguous keys</span></span>

<span data-ttu-id="d7eb8-104">Nell'esempio seguente viene illustrato come raggruppare elementi in blocchi che rappresentano sottosequenze di chiavi contigue.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="d7eb8-105">Si supponga di avere ad esempio la sequenza di coppie chiave-valore riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="d7eb8-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="d7eb8-106">Chiave</span><span class="sxs-lookup"><span data-stu-id="d7eb8-106">Key</span></span>|<span data-ttu-id="d7eb8-107">Valore</span><span class="sxs-lookup"><span data-stu-id="d7eb8-107">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="d7eb8-108">A</span><span class="sxs-lookup"><span data-stu-id="d7eb8-108">A</span></span>|<span data-ttu-id="d7eb8-109">Me</span><span class="sxs-lookup"><span data-stu-id="d7eb8-109">We</span></span>|  
|<span data-ttu-id="d7eb8-110">A</span><span class="sxs-lookup"><span data-stu-id="d7eb8-110">A</span></span>|<span data-ttu-id="d7eb8-111">think</span><span class="sxs-lookup"><span data-stu-id="d7eb8-111">think</span></span>|  
|<span data-ttu-id="d7eb8-112">A</span><span class="sxs-lookup"><span data-stu-id="d7eb8-112">A</span></span>|<span data-ttu-id="d7eb8-113">that</span><span class="sxs-lookup"><span data-stu-id="d7eb8-113">that</span></span>|  
|<span data-ttu-id="d7eb8-114">B</span><span class="sxs-lookup"><span data-stu-id="d7eb8-114">B</span></span>|<span data-ttu-id="d7eb8-115">Linq</span><span class="sxs-lookup"><span data-stu-id="d7eb8-115">Linq</span></span>|  
|<span data-ttu-id="d7eb8-116">C</span><span class="sxs-lookup"><span data-stu-id="d7eb8-116">C</span></span>|<span data-ttu-id="d7eb8-117">is</span><span class="sxs-lookup"><span data-stu-id="d7eb8-117">is</span></span>|  
|<span data-ttu-id="d7eb8-118">A</span><span class="sxs-lookup"><span data-stu-id="d7eb8-118">A</span></span>|<span data-ttu-id="d7eb8-119">really</span><span class="sxs-lookup"><span data-stu-id="d7eb8-119">really</span></span>|  
|<span data-ttu-id="d7eb8-120">B</span><span class="sxs-lookup"><span data-stu-id="d7eb8-120">B</span></span>|<span data-ttu-id="d7eb8-121">cool</span><span class="sxs-lookup"><span data-stu-id="d7eb8-121">cool</span></span>|  
|<span data-ttu-id="d7eb8-122">B</span><span class="sxs-lookup"><span data-stu-id="d7eb8-122">B</span></span>|<span data-ttu-id="d7eb8-123">!</span><span class="sxs-lookup"><span data-stu-id="d7eb8-123">!</span></span>|  
  
 <span data-ttu-id="d7eb8-124">Verranno creati i gruppi seguenti in questo ordine:</span><span class="sxs-lookup"><span data-stu-id="d7eb8-124">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="d7eb8-125">We, think, that</span><span class="sxs-lookup"><span data-stu-id="d7eb8-125">We, think, that</span></span>  
  
2.  <span data-ttu-id="d7eb8-126">Linq</span><span class="sxs-lookup"><span data-stu-id="d7eb8-126">Linq</span></span>  
  
3.  <span data-ttu-id="d7eb8-127">is</span><span class="sxs-lookup"><span data-stu-id="d7eb8-127">is</span></span>  
  
4.  <span data-ttu-id="d7eb8-128">really</span><span class="sxs-lookup"><span data-stu-id="d7eb8-128">really</span></span>  
  
5.  <span data-ttu-id="d7eb8-129">cool, !</span><span class="sxs-lookup"><span data-stu-id="d7eb8-129">cool, !</span></span>  
  
 <span data-ttu-id="d7eb8-130">La soluzione viene implementata come metodo di estensione thread-safe che restituisce i risultati in modalità di flusso.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="d7eb8-131">In altre parole, i gruppi vengono prodotti man mano che ci si sposta lungo la sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="d7eb8-132">A differenza degli operatori `group` o `orderby`, questa soluzione può iniziare a restituire i gruppi al chiamante prima che sia stata letta tutta la sequenza.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="d7eb8-133">La caratteristica thread-safe viene ottenuta effettuando una copia di ogni gruppo o blocco nel corso dell'iterazione della sequenza di origine, come spiegato nei commenti del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="d7eb8-134">Se la sequenza di origine include una sequenza di grandi dimensioni di elementi contigui, Common Language Runtime potrebbe generare un'eccezione <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7eb8-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7eb8-135">Example</span></span>  
 <span data-ttu-id="d7eb8-136">Nell'esempio seguente viene illustrato sia il metodo di estensione che il codice client usato.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-136">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="d7eb8-137">Per usare il metodo di estensione nel progetto, copiare la classe statica `MyExtensions` in un file di codice sorgente nuovo o esistente e, se richiesto, aggiungere una direttiva `using` per lo spazio dei nomi in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="d7eb8-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7eb8-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7eb8-138">See also</span></span>  
 [<span data-ttu-id="d7eb8-139">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="d7eb8-139">LINQ Query Expressions</span></span>](index.md)  
 
