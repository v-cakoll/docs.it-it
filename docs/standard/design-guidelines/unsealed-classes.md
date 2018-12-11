---
title: Classi non sealed
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: 8d7b1500506ec73a0d33d5352756cb85039358e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153228"
---
# <a name="unsealed-classes"></a><span data-ttu-id="79b54-102">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="79b54-102">Unsealed Classes</span></span>
<span data-ttu-id="79b54-103">Le classi sealed non possono essere ereditate da, e consentirne l'estendibilità.</span><span class="sxs-lookup"><span data-stu-id="79b54-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="79b54-104">Al contrario, le classi che possono essere ereditate da vengono denominate classi non sealed.</span><span class="sxs-lookup"><span data-stu-id="79b54-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="79b54-105">**✓ CONSIDER** utilizzando classi non sealed con nessuna aggiunti i membri virtuali o protetti come un ottimo modo per fornire a basso costo ancora molto apprezzato estensibilità per un framework.</span><span class="sxs-lookup"><span data-stu-id="79b54-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="79b54-106">Gli sviluppatori spesso vogliono ereditare da classi non sealed in modo da aggiungere i membri di praticità, ad esempio costruttori personalizzati, nuovi metodi o gli overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="79b54-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="79b54-107">Ad esempio, `System.Messaging.MessageQueue` è bloccato e pertanto consente agli utenti di creare code personalizzate che per impostazione predefinita un percorso della coda specifica o per aggiungere metodi personalizzati che consentono di semplificare l'API per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="79b54-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="79b54-108">Le classi sono sealed o non sealed per impostazione predefinita nei linguaggi di programmazione più, e questo è anche l'impostazione predefinita consigliata per la maggior parte delle classi nel Framework.</span><span class="sxs-lookup"><span data-stu-id="79b54-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="79b54-109">L'estendibilità ottenibili da tipi non sealed è molto apprezzato dagli utenti di framework e molto conveniente fornire a causa dei costi relativamente basso di test associati ai tipi non sealed.</span><span class="sxs-lookup"><span data-stu-id="79b54-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="79b54-110">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="79b54-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="79b54-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="79b54-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b54-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79b54-112">See also</span></span>

- [<span data-ttu-id="79b54-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="79b54-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="79b54-114">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="79b54-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [<span data-ttu-id="79b54-115">Sealing</span><span class="sxs-lookup"><span data-stu-id="79b54-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
