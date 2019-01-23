---
title: Membri protetti
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559341"
---
# <a name="protected-members"></a><span data-ttu-id="5571e-102">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="5571e-102">Protected Members</span></span>
<span data-ttu-id="5571e-103">Membri protetti da soli non forniscono alcun estendibilità, ma estendibilità tramite la creazione di sottoclassi può rendere più potenti.</span><span class="sxs-lookup"><span data-stu-id="5571e-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="5571e-104">Possono essere utilizzati per esporre le opzioni di personalizzazione avanzate senza complicare inutilmente l'interfaccia pubblica principale.</span><span class="sxs-lookup"><span data-stu-id="5571e-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="5571e-105">Le finestre di progettazione di Framework necessario prestare attenzione con i membri protetti perché il nome "protetto" può dare un senso di protezione fasullo.</span><span class="sxs-lookup"><span data-stu-id="5571e-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="5571e-106">Chiunque sia in grado di sottoclasse di una classe non sealed e protetta con accesso membri e quindi le stesse procedure di codifica difensive utilizzate per i membri pubblici applicano ai membri protetti.</span><span class="sxs-lookup"><span data-stu-id="5571e-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="5571e-107">**✓ CONSIDER** utilizzando membri per la personalizzazione avanzata protetti.</span><span class="sxs-lookup"><span data-stu-id="5571e-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="5571e-108">**✓ DO** trattare i membri protetti nelle classi non sealed come public allo scopo di analisi di sicurezza, documentazione e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5571e-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="5571e-109">Chiunque può ereditare da una classe e accedere ai membri protetti.</span><span class="sxs-lookup"><span data-stu-id="5571e-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="5571e-110">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="5571e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5571e-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5571e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5571e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5571e-112">See also</span></span>

- [<span data-ttu-id="5571e-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="5571e-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="5571e-114">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="5571e-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
