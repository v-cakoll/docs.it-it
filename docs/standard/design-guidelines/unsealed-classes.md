---
title: Classi non sealed
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 6804a79e8beee1d42e313509966b46239e66c25f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743558"
---
# <a name="unsealed-classes"></a><span data-ttu-id="dd076-102">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="dd076-102">Unsealed Classes</span></span>
<span data-ttu-id="dd076-103">Le classi sealed non possono essere ereditate da e impediscono l'estensibilità.</span><span class="sxs-lookup"><span data-stu-id="dd076-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="dd076-104">Al contrario, le classi che possono essere ereditate da sono denominate classi non sealed.</span><span class="sxs-lookup"><span data-stu-id="dd076-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="dd076-105">✔️ CONSIGLIABILE utilizzare classi non sealed senza membri virtuali o protetti aggiunti come un ottimo modo per offrire un'estendibilità economica ma molto apprezzata a un Framework.</span><span class="sxs-lookup"><span data-stu-id="dd076-105">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="dd076-106">Gli sviluppatori spesso desiderano ereditare da classi non sealed per aggiungere pratici membri, ad esempio costruttori personalizzati, nuovi metodi o overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="dd076-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="dd076-107">Ad esempio, `System.Messaging.MessageQueue` non è sealed e quindi consente agli utenti di creare code personalizzate per impostazione predefinita su un determinato percorso della coda o di aggiungere metodi personalizzati che semplificano l'API per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="dd076-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="dd076-108">Per impostazione predefinita, le classi sono non sealed nella maggior parte dei linguaggi di programmazione ed è anche l'impostazione predefinita consigliata per la maggior parte delle classi nei Framework.</span><span class="sxs-lookup"><span data-stu-id="dd076-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="dd076-109">L'estendibilità garantita dai tipi non sealed è molto apprezzata dagli utenti del Framework e piuttosto economica da fornire a causa dei costi di test relativamente bassi associati ai tipi non sealed.</span><span class="sxs-lookup"><span data-stu-id="dd076-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="dd076-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="dd076-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="dd076-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="dd076-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="dd076-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd076-112">See also</span></span>

- [<span data-ttu-id="dd076-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="dd076-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="dd076-114">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="dd076-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="dd076-115">Sealing</span><span class="sxs-lookup"><span data-stu-id="dd076-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
