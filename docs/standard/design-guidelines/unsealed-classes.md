---
title: Classi non sealed
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571661"
---
# <a name="unsealed-classes"></a><span data-ttu-id="bc61f-102">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="bc61f-102">Unsealed Classes</span></span>
<span data-ttu-id="bc61f-103">Classi sealed non possono essere ereditate da e impediscono l'estensibilità.</span><span class="sxs-lookup"><span data-stu-id="bc61f-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="bc61f-104">Al contrario, le classi che possono essere ereditate da sono dette classi non sealed.</span><span class="sxs-lookup"><span data-stu-id="bc61f-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="bc61f-105">**✓ Provare a** utilizzando classi non sealed con nessuna aggiunti i membri virtuali o protetti come un ottimo modo per fornire a basso costo ancora molto apprezzato estensibilità per un framework.</span><span class="sxs-lookup"><span data-stu-id="bc61f-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="bc61f-106">Gli sviluppatori spesso necessario ereditare da classi non sealed in modo da aggiungere i membri di praticità, ad esempio l'overload del metodo, nuovi metodi o costruttori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="bc61f-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="bc61f-107">Ad esempio, `System.Messaging.MessageQueue` non bloccato e pertanto consente agli utenti di creare code personalizzate tale impostazione predefinita a un percorso di coda specifica o per aggiungere metodi personalizzati che semplificano l'API per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="bc61f-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="bc61f-108">Le classi sono non sealed per impostazione predefinita nei linguaggi di programmazione più, e questo è il valore predefinito consigliato per la maggior parte delle classi in Framework.</span><span class="sxs-lookup"><span data-stu-id="bc61f-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="bc61f-109">L'estendibilità offerta dal tipi non sealed è molto apprezzato dagli utenti framework e molto costosi da fornire a causa dei costi relativamente basso di test associati a tipi non sealed.</span><span class="sxs-lookup"><span data-stu-id="bc61f-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="bc61f-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="bc61f-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bc61f-111">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bc61f-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc61f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc61f-112">See Also</span></span>  
 [<span data-ttu-id="bc61f-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="bc61f-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="bc61f-114">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="bc61f-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="bc61f-115">Sealing</span><span class="sxs-lookup"><span data-stu-id="bc61f-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
