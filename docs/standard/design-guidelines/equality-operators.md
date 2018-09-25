---
title: Operatori di uguaglianza
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27550a8fd8292029cad9c2e699374a190b1a532e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088074"
---
# <a name="equality-operators"></a><span data-ttu-id="0a997-102">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="0a997-102">Equality Operators</span></span>
<span data-ttu-id="0a997-103">In questa sezione illustra l'overload degli operatori di uguaglianza e si intende `operator==` e `operator!=` come operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="0a997-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="0a997-104">**X DO NOT** overload degli operatori di uguaglianza e non in altro.</span><span class="sxs-lookup"><span data-stu-id="0a997-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="0a997-105">**✓ DO** assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza hanno esattamente la stessa semantica e caratteristiche di prestazioni simili.</span><span class="sxs-lookup"><span data-stu-id="0a997-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="0a997-106">Ciò significa che spesso `Object.Equals` deve essere sottoposto a override quando sono sottoposti a overload gli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="0a997-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="0a997-107">**X AVOID** generazione di eccezioni da operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="0a997-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="0a997-108">Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="0a997-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="0a997-109">Operatori di uguaglianza sui tipi di valore</span><span class="sxs-lookup"><span data-stu-id="0a997-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="0a997-110">**✓ DO** eseguire l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativo.</span><span class="sxs-lookup"><span data-stu-id="0a997-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="0a997-111">La maggior parte dei linguaggi di programmazione, vi è Nessuna implementazione predefinita di `operator==` per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="0a997-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="0a997-112">Operatori di uguaglianza sui tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="0a997-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="0a997-113">**X AVOID** overload degli operatori di uguaglianza sui tipi di riferimento modificabile.</span><span class="sxs-lookup"><span data-stu-id="0a997-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="0a997-114">Molte lingue hanno operatori di uguaglianza predefinito per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0a997-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="0a997-115">Gli operatori incorporati in genere implementano l'uguaglianza di riferimenti e molti sviluppatori sono sorpresi quando viene modificato il comportamento predefinito per l'uguaglianza di valore.</span><span class="sxs-lookup"><span data-stu-id="0a997-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="0a997-116">Questo problema è stata risolta per i tipi di riferimento non modificabile, poiché non modificabilità rende molto più difficile da osservare la differenza tra uguaglianza di riferimento e uguaglianza di valori.</span><span class="sxs-lookup"><span data-stu-id="0a997-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="0a997-117">**X AVOID** overload degli operatori di uguaglianza sui tipi di riferimento se l'implementazione sarebbe notevolmente più lento rispetto a quello di uguaglianza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0a997-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="0a997-118">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="0a997-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0a997-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="0a997-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a997-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a997-120">See also</span></span>

- [<span data-ttu-id="0a997-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="0a997-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="0a997-122">Linee guida per l'uso</span><span class="sxs-lookup"><span data-stu-id="0a997-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
