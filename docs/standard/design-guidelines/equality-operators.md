---
title: Operatori di uguaglianza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55c0505f5a06dfc87897fa59e9d6083cbd63c8ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="equality-operators"></a><span data-ttu-id="04e70-102">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="04e70-102">Equality Operators</span></span>
<span data-ttu-id="04e70-103">In questa sezione illustra l'overload degli operatori di uguaglianza e fa riferimento a `operator==` e `operator!=` come operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="04e70-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="04e70-104">**X non** overload degli operatori di uguaglianza e non in altro.</span><span class="sxs-lookup"><span data-stu-id="04e70-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="04e70-105">**✓ SI** assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza esattamente la stessa semantica e caratteristiche di prestazioni simili.</span><span class="sxs-lookup"><span data-stu-id="04e70-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="04e70-106">Ciò significa che spesso `Object.Equals` deve essere sottoposto a override quando sono sottoposti a overload gli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="04e70-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="04e70-107">**X evitare** generazione di eccezioni da operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="04e70-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="04e70-108">Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="04e70-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="04e70-109">Operatori di uguaglianza sui tipi di valore</span><span class="sxs-lookup"><span data-stu-id="04e70-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="04e70-110">**✓ SI** eseguire l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativo.</span><span class="sxs-lookup"><span data-stu-id="04e70-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="04e70-111">La maggior parte dei linguaggi di programmazione, non vi è Nessuna implementazione predefinita di `operator==` per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="04e70-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="04e70-112">Operatori di uguaglianza sui tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="04e70-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="04e70-113">**X evitare** overload degli operatori di uguaglianza sui tipi di riferimento modificabile.</span><span class="sxs-lookup"><span data-stu-id="04e70-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="04e70-114">Molte lingue hanno operatori di uguaglianza predefinito per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="04e70-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="04e70-115">Gli operatori incorporati in genere implementano l'uguaglianza di riferimento e molti sviluppatori sono testati quando viene modificato il comportamento predefinito per l'uguaglianza di valore.</span><span class="sxs-lookup"><span data-stu-id="04e70-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="04e70-116">Questo problema viene ridotta per i tipi di riferimento non modificabile in quanto rende molto più difficile da notare la differenza tra uguaglianza di riferimento e uguaglianza immutabilità.</span><span class="sxs-lookup"><span data-stu-id="04e70-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="04e70-117">**X evitare** overload degli operatori di uguaglianza sui tipi di riferimento, se l'implementazione è notevolmente più lento rispetto a quello di uguaglianza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="04e70-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="04e70-118">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="04e70-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="04e70-119">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="04e70-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e70-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04e70-120">See Also</span></span>  
 [<span data-ttu-id="04e70-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="04e70-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="04e70-122">Linee guida di utilizzo</span><span class="sxs-lookup"><span data-stu-id="04e70-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
