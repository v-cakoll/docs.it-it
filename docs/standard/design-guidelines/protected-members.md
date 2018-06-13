---
title: Membri protetti
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571085"
---
# <a name="protected-members"></a><span data-ttu-id="476a1-102">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="476a1-102">Protected Members</span></span>
<span data-ttu-id="476a1-103">Membri protetti da soli non forniscono alcun estendibilità, ma può rendere più potente di estendibilità tramite la creazione di sottoclassi.</span><span class="sxs-lookup"><span data-stu-id="476a1-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="476a1-104">Possono essere utilizzati per esporre le opzioni di personalizzazione avanzate senza inutilmente complica l'interfaccia pubblica principale.</span><span class="sxs-lookup"><span data-stu-id="476a1-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="476a1-105">Finestre di progettazione Framework necessario prestare attenzione ai membri protetti perché il nome "protetto" può concedere a un falso senso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="476a1-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="476a1-106">Chiunque sia in grado di sottoclasse di una classe non sealed e i membri di accesso protetto e pertanto le stesse difensivo procedure di codifica utilizzati per i membri pubblici applicano ai membri protetti.</span><span class="sxs-lookup"><span data-stu-id="476a1-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="476a1-107">**✓ Provare a** utilizzando membri per la personalizzazione avanzata protetti.</span><span class="sxs-lookup"><span data-stu-id="476a1-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="476a1-108">**✓ SI** trattare i membri protetti nelle classi non sealed come public allo scopo di analisi di sicurezza, documentazione e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="476a1-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="476a1-109">Chiunque può ereditare da una classe e accedere ai membri protetti.</span><span class="sxs-lookup"><span data-stu-id="476a1-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="476a1-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="476a1-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="476a1-111">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="476a1-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476a1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="476a1-112">See Also</span></span>  
 [<span data-ttu-id="476a1-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="476a1-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="476a1-114">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="476a1-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
