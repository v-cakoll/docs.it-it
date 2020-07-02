---
title: Membri virtuali
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 918208bb44f84988b7fe903c589e82c7bf1f59e3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620768"
---
# <a name="virtual-members"></a><span data-ttu-id="8271e-102">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="8271e-102">Virtual Members</span></span>
<span data-ttu-id="8271e-103">È possibile eseguire l'override dei membri virtuali, modificando in tal modo il comportamento della sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="8271e-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="8271e-104">Sono molto simili alle richiamate in termini di estendibilità che forniscono, ma sono migliori in termini di prestazioni di esecuzione e di utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="8271e-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="8271e-105">Inoltre, i membri virtuali si sentono più naturali negli scenari che richiedono la creazione di un tipo speciale di un tipo esistente (specializzazione).</span><span class="sxs-lookup"><span data-stu-id="8271e-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>

 <span data-ttu-id="8271e-106">I membri virtuali offrono prestazioni migliori rispetto a callback ed eventi, ma non offrono prestazioni migliori rispetto ai metodi non virtuali.</span><span class="sxs-lookup"><span data-stu-id="8271e-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>

 <span data-ttu-id="8271e-107">Lo svantaggio principale dei membri virtuali è che il comportamento di un membro virtuale può essere modificato solo al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="8271e-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="8271e-108">Il comportamento di un callback può essere modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8271e-108">The behavior of a callback can be modified at runtime.</span></span>

 <span data-ttu-id="8271e-109">I membri virtuali, ad esempio i callback (e forse più di callback), sono costosi da progettare, testare e gestire perché qualsiasi chiamata a un membro virtuale può essere sottoposta a override in modi imprevedibili ed è in grado di eseguire codice arbitrario.</span><span class="sxs-lookup"><span data-stu-id="8271e-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="8271e-110">Inoltre, la maggior parte degli sforzi è in genere necessaria per definire chiaramente il contratto dei membri virtuali, quindi il costo della progettazione e della relativa documentazione è superiore.</span><span class="sxs-lookup"><span data-stu-id="8271e-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>

 <span data-ttu-id="8271e-111">❌NON rendere virtuali i membri, a meno che non si disponga di un motivo valido e si siano consapevoli di tutti i costi correlati alla progettazione, al test e alla gestione dei membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="8271e-111">❌ DO NOT make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>

 <span data-ttu-id="8271e-112">I membri virtuali sono meno indulgenti in termini di modifiche che possono essere apportate senza interruzioni della compatibilità.</span><span class="sxs-lookup"><span data-stu-id="8271e-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="8271e-113">Sono inoltre più lenti dei membri non virtuali, soprattutto perché le chiamate a membri virtuali non sono inline.</span><span class="sxs-lookup"><span data-stu-id="8271e-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>

 <span data-ttu-id="8271e-114">✔️ CONSIGLIABILE limitare l'estendibilità solo a ciò che è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="8271e-114">✔️ CONSIDER limiting extensibility to only what is absolutely necessary.</span></span>

 <span data-ttu-id="8271e-115">✔️ preferisci l'accessibilità protetta sull'accessibilità pubblica per i membri virtuali.</span><span class="sxs-lookup"><span data-stu-id="8271e-115">✔️ DO prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="8271e-116">I membri pubblici devono fornire estensibilità (se necessario) chiamando un membro virtuale protetto.</span><span class="sxs-lookup"><span data-stu-id="8271e-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>

 <span data-ttu-id="8271e-117">I membri pubblici di una classe devono fornire il set corretto di funzionalità per i consumer diretti di tale classe.</span><span class="sxs-lookup"><span data-stu-id="8271e-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="8271e-118">I membri virtuali sono progettati per essere sottoposti a override nelle sottoclassi e l'accessibilità protetta è un ottimo modo per definire l'ambito di tutti i punti di estendibilità virtuali in cui possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="8271e-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>

 <span data-ttu-id="8271e-119">*Parti &copy; 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8271e-119">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8271e-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8271e-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8271e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8271e-121">See also</span></span>

- [<span data-ttu-id="8271e-122">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8271e-122">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="8271e-123">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="8271e-123">Designing for Extensibility</span></span>](designing-for-extensibility.md)
