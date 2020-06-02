---
title: Operatori di uguaglianza
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: bd36b98af25db2921c164ac359188997d379a270
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280050"
---
# <a name="equality-operators"></a><span data-ttu-id="d724d-102">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="d724d-102">Equality Operators</span></span>
<span data-ttu-id="d724d-103">In questa sezione viene illustrato l'overload degli operatori di uguaglianza e si fa riferimento a `operator==` e `operator!=` come operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="d724d-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="d724d-104">❌Non eseguire l'overload di uno degli operatori di uguaglianza e non dell'altro.</span><span class="sxs-lookup"><span data-stu-id="d724d-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="d724d-105">✔️ Assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza abbiano esattamente la stessa semantica e caratteristiche di prestazioni simili.</span><span class="sxs-lookup"><span data-stu-id="d724d-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="d724d-106">Questo significa spesso che `Object.Equals` deve essere sottoposto a override quando gli operatori di uguaglianza sono sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="d724d-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="d724d-107">❌EVITARE di generare eccezioni dagli operatori di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="d724d-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="d724d-108">Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException` .</span><span class="sxs-lookup"><span data-stu-id="d724d-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="d724d-109">Operatori di uguaglianza sui tipi di valore</span><span class="sxs-lookup"><span data-stu-id="d724d-109">Equality Operators on Value Types</span></span>
 <span data-ttu-id="d724d-110">✔️ ESEGUONO l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativa.</span><span class="sxs-lookup"><span data-stu-id="d724d-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="d724d-111">Nella maggior parte dei linguaggi di programmazione non è disponibile un'implementazione predefinita di `operator==` per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d724d-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="d724d-112">Operatori di uguaglianza sui tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="d724d-112">Equality Operators on Reference Types</span></span>
 <span data-ttu-id="d724d-113">❌EVITARE l'overload degli operatori di uguaglianza sui tipi di riferimento modificabili.</span><span class="sxs-lookup"><span data-stu-id="d724d-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="d724d-114">Molti linguaggi hanno operatori di uguaglianza predefiniti per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d724d-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="d724d-115">Gli operatori incorporati in genere implementano l'uguaglianza dei riferimenti e molti sviluppatori sono sorpresi quando il comportamento predefinito viene modificato nell'uguaglianza dei valori.</span><span class="sxs-lookup"><span data-stu-id="d724d-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="d724d-116">Questo problema è mitigato per i tipi di riferimento non modificabili perché l'immutabilità rende molto più difficile notare la differenza tra uguaglianza dei riferimenti e uguaglianza dei valori.</span><span class="sxs-lookup"><span data-stu-id="d724d-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="d724d-117">❌EVITARE l'overload degli operatori di uguaglianza sui tipi di riferimento se l'implementazione è significativamente più lenta rispetto a quella dell'uguaglianza dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d724d-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="d724d-118">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d724d-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d724d-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d724d-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d724d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d724d-120">See also</span></span>

- [<span data-ttu-id="d724d-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d724d-121">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d724d-122">Linee guida sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="d724d-122">Usage Guidelines</span></span>](usage-guidelines.md)
