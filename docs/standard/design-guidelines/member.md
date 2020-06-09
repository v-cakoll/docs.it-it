---
title: Linee guida di progettazione dei membri
description: Informazioni sulle linee guida per la progettazione di membri in .NET. I membri includono metodi, proprietà, eventi, costruttori e campi.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: a1f0c1d74e8bffa7cfef975c7dafb9fd01479470
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594491"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="577bc-104">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="577bc-104">Member Design Guidelines</span></span>
<span data-ttu-id="577bc-105">Metodi, proprietà, eventi, costruttori e campi vengono collettivamente definiti membri.</span><span class="sxs-lookup"><span data-stu-id="577bc-105">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="577bc-106">I membri sono infine i mezzi con cui la funzionalità del Framework viene esposta agli utenti finali di un Framework.</span><span class="sxs-lookup"><span data-stu-id="577bc-106">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="577bc-107">I membri possono essere virtuali o non virtuali, concreti, astratti, statici o di istanza e possono avere diversi ambiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="577bc-107">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="577bc-108">Questa varietà fornisce un'espressività incredibile, ma allo stesso tempo richiede attenzione da parte di progettazione Framework.</span><span class="sxs-lookup"><span data-stu-id="577bc-108">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="577bc-109">In questo capitolo vengono fornite le linee guida di base da seguire per la progettazione di membri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="577bc-109">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="577bc-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="577bc-110">In This Section</span></span>  
 [<span data-ttu-id="577bc-111">Overload di membri</span><span class="sxs-lookup"><span data-stu-id="577bc-111">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="577bc-112">Progettazione di proprietà</span><span class="sxs-lookup"><span data-stu-id="577bc-112">Property Design</span></span>](property.md)  
 [<span data-ttu-id="577bc-113">Progettazione di costruttori</span><span class="sxs-lookup"><span data-stu-id="577bc-113">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="577bc-114">Progettazione di eventi</span><span class="sxs-lookup"><span data-stu-id="577bc-114">Event Design</span></span>](event.md)  
 [<span data-ttu-id="577bc-115">Progettazione campi</span><span class="sxs-lookup"><span data-stu-id="577bc-115">Field Design</span></span>](field.md)  
 [<span data-ttu-id="577bc-116">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="577bc-116">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="577bc-117">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="577bc-117">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="577bc-118">Progettazione di parametri</span><span class="sxs-lookup"><span data-stu-id="577bc-118">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="577bc-119">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="577bc-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="577bc-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="577bc-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577bc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="577bc-121">See also</span></span>

- [<span data-ttu-id="577bc-122">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="577bc-122">Framework Design Guidelines</span></span>](index.md)
