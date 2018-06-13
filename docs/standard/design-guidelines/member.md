---
title: Linee guida di progettazione dei membri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c04b431224a1d4f03e85397b854a52856e114e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571397"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="f1d26-102">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="f1d26-102">Member Design Guidelines</span></span>
<span data-ttu-id="f1d26-103">Metodi, proprietà, eventi, costruttori e i campi vengono collettivamente come membri.</span><span class="sxs-lookup"><span data-stu-id="f1d26-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="f1d26-104">Infine, i membri sono i mezzi mediante il quale framework funzionalità esposta agli utenti finali di un framework.</span><span class="sxs-lookup"><span data-stu-id="f1d26-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="f1d26-105">I membri possono essere virtuale o non virtuali, concreto o astratti, statico o istanza e possono avere diversi ambiti diversi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="f1d26-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="f1d26-106">Tutte le serie di questo fornisce espressività incredibile ma allo stesso tempo richiede attenzione da parte di finestra di progettazione di framework.</span><span class="sxs-lookup"><span data-stu-id="f1d26-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="f1d26-107">In questo capitolo offre linee guida di base da seguire quando si progettano i membri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="f1d26-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1d26-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f1d26-108">In This Section</span></span>  
 [<span data-ttu-id="f1d26-109">Overload dei membri</span><span class="sxs-lookup"><span data-stu-id="f1d26-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="f1d26-110">Progettazione di proprietà</span><span class="sxs-lookup"><span data-stu-id="f1d26-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="f1d26-111">Progettazione di costruttori</span><span class="sxs-lookup"><span data-stu-id="f1d26-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="f1d26-112">Progettazione di eventi</span><span class="sxs-lookup"><span data-stu-id="f1d26-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="f1d26-113">Progettazione di campi</span><span class="sxs-lookup"><span data-stu-id="f1d26-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="f1d26-114">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="f1d26-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="f1d26-115">Overload dell'operatore</span><span class="sxs-lookup"><span data-stu-id="f1d26-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="f1d26-116">Progettazione di parametri</span><span class="sxs-lookup"><span data-stu-id="f1d26-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="f1d26-117">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="f1d26-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f1d26-118">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f1d26-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d26-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d26-119">See Also</span></span>  
 [<span data-ttu-id="f1d26-120">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="f1d26-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
