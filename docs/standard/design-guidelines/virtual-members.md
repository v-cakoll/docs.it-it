---
title: Membri virtuali
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 1719e9843252c25d1e799471330c6cb08211245b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128927"
---
# <a name="virtual-members"></a><span data-ttu-id="9ae50-102">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="9ae50-102">Virtual Members</span></span>
<span data-ttu-id="9ae50-103">Membri virtuali possono essere sottoposto a override, in modo da modificarne il comportamento della sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="9ae50-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="9ae50-104">Sono molto simili ai callback in termini di estensibilità che forniscono, ma sono migliori in termini di prestazioni di esecuzione e il consumo di memoria.</span><span class="sxs-lookup"><span data-stu-id="9ae50-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="9ae50-105">Inoltre, i membri virtuali sembrano più naturali negli scenari che richiedono la creazione di uno speciale tipo di un tipo esistente (specializzazione).</span><span class="sxs-lookup"><span data-stu-id="9ae50-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="9ae50-106">Membri virtuali offrono prestazioni migliori rispetto a callback ed eventi, ma non offrono prestazioni migliori rispetto ai metodi non virtuali.</span><span class="sxs-lookup"><span data-stu-id="9ae50-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="9ae50-107">Lo svantaggio principale di membri virtuali è che il comportamento di un membro virtuale può essere modificato solo al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="9ae50-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="9ae50-108">Il comportamento di un callback può essere modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9ae50-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="9ae50-109">Membri virtuali, ad esempio i callback e forse più di callback, sono anche costosi da progettare, testare e gestire perché tutte le chiamate a un membro virtuale possono essere sottoposto a override in modo imprevedibile e possono eseguire codice arbitrario.</span><span class="sxs-lookup"><span data-stu-id="9ae50-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="9ae50-110">È inoltre molto più complessa è generalmente necessaria per definire chiaramente il contratto dei membri virtuali, in modo che il costo di progettazione e la documentazione di essi è elevato.</span><span class="sxs-lookup"><span data-stu-id="9ae50-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="9ae50-111">**X DO NOT** rendere i membri virtuali a meno che non si dispone di un buon motivo per eseguire questa operazione e di essere a conoscenza di tutti i costi correlati alla progettazione, test e la gestione di membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="9ae50-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="9ae50-112">Membri virtuali sono meno tollerante in termini di modifiche che possono essere eseguite a loro senza compromettere la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="9ae50-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="9ae50-113">Inoltre, sono più lenti rispetto a membri non virtuale, principalmente perché le chiamate a membri virtuali non vengono impostati come inline.</span><span class="sxs-lookup"><span data-stu-id="9ae50-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="9ae50-114">**✓ CONSIDER** limitazione estendibilità solo a quelle strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="9ae50-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="9ae50-115">**✓ DO** preferire accessibilità protetta accessibilità pubblica per i membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="9ae50-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="9ae50-116">I membri pubblici devono fornire estendibilità (se richiesto) effettuando la chiamata a un membro virtuale protetta.</span><span class="sxs-lookup"><span data-stu-id="9ae50-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="9ae50-117">I membri pubblici di una classe devono fornire il set corretto di funzionalità per i consumer diretti di tale classe.</span><span class="sxs-lookup"><span data-stu-id="9ae50-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="9ae50-118">Membri virtuali sono progettati per essere sottoposto a override nelle sottoclassi e accessibilità protetta è un ottimo modo per definire l'ambito di tutti i punti di estendibilità virtuale a cui potranno essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="9ae50-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="9ae50-119">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="9ae50-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9ae50-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9ae50-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae50-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ae50-121">See also</span></span>

- [<span data-ttu-id="9ae50-122">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="9ae50-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="9ae50-123">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="9ae50-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
