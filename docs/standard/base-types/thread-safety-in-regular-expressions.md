---
title: Thread safety nelle espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4cfa24da8083eac01275ad76f5c2db974b39a25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="thread-safety-in-regular-expressions"></a><span data-ttu-id="21d2e-102">Thread safety nelle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="21d2e-102">Thread Safety in Regular Expressions</span></span>
<span data-ttu-id="21d2e-103">La <xref:System.Text.RegularExpressions.Regex> classe stessa è thread-safe e non modificabile (sola lettura).</span><span class="sxs-lookup"><span data-stu-id="21d2e-103">The <xref:System.Text.RegularExpressions.Regex> class itself is thread safe and immutable (read-only).</span></span> <span data-ttu-id="21d2e-104">Ciò significa che è possibile creare oggetti **Regex** in qualsiasi thread e condividerli fra i thread; i metodi corrispondenti possono essere chiamati da qualsiasi thread e non modificano in nessun caso uno stato globale.</span><span class="sxs-lookup"><span data-stu-id="21d2e-104">That is, **Regex** objects can be created on any thread and shared between threads; matching methods can be called from any thread and never alter any global state.</span></span>  
  
 <span data-ttu-id="21d2e-105">Tuttavia, gli oggetti di risultato (**corrispondenza** e **MatchCollection**) restituito da **Regex** deve essere usato su un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="21d2e-105">However, result objects (**Match** and **MatchCollection**) returned by **Regex** should be used on a single thread.</span></span> <span data-ttu-id="21d2e-106">Sebbene molti di questi oggetti non siano modificabili a livello logico, le loro implementazioni potrebbero ritardare l'elaborazione di determinati risultati per migliorare le prestazioni; di conseguenza, i chiamanti dovranno serializzare l'accesso a tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="21d2e-106">Although many of these objects are logically immutable, their implementations could delay computation of some results to improve performance, and as a result, callers must serialize access to them.</span></span>  
  
 <span data-ttu-id="21d2e-107">Se risulta necessario condividere oggetti risultato **Regex** su più thread, tali oggetti possono essere convertiti in istanze thread-safe chiamando i relativi metodi sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="21d2e-107">If there is a need to share **Regex** result objects on multiple threads, these objects can be converted to thread-safe instances by calling their synchronized methods.</span></span> <span data-ttu-id="21d2e-108">Fatta eccezione per gli enumeratori, tutte le classi di espressioni regolari sono thread-safe o possono essere convertite in oggetti thread-safe mediante un metodo sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="21d2e-108">With the exception of enumerators, all regular expression classes are thread safe or can be converted into thread-safe objects by a synchronized method.</span></span>  
  
 <span data-ttu-id="21d2e-109">L'unica eccezione è costituita dagli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="21d2e-109">Enumerators are the only exception.</span></span> <span data-ttu-id="21d2e-110">Un'applicazione deve serializzare le chiamate agli enumeratori di raccolta.</span><span class="sxs-lookup"><span data-stu-id="21d2e-110">An application must serialize calls to collection enumerators.</span></span> <span data-ttu-id="21d2e-111">La regola indica che se una raccolta può essere enumerata in più thread contemporaneamente, è necessario sincronizzare i metodi di enumeratore sull'oggetto radice della raccolta attraversata dall'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="21d2e-111">The rule is that if a collection can be enumerated on more than one thread simultaneously, you should synchronize enumerator methods on the root object of the collection traversed by the enumerator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d2e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21d2e-112">See Also</span></span>  
 [<span data-ttu-id="21d2e-113">Espressioni regolari di .NET</span><span class="sxs-lookup"><span data-stu-id="21d2e-113">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
