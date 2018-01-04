---
title: Denominazione di risorse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0387d820cc660bdf6cbafb9d76bbf0184c111881
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="naming-resources"></a><span data-ttu-id="362ab-102">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="362ab-102">Naming Resources</span></span>
<span data-ttu-id="362ab-103">Poiché possono fare riferimento a risorse localizzabili mediante determinati oggetti come se fossero proprietà, convenzioni di denominazione per le risorse sono simili alle linee guida di proprietà.</span><span class="sxs-lookup"><span data-stu-id="362ab-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="362ab-104">**✓ SI** utilizzare il sistema Pascal le chiavi di risorsa.</span><span class="sxs-lookup"><span data-stu-id="362ab-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="362ab-105">**✓ SI** fornire descrittivo anziché identificatori breve.</span><span class="sxs-lookup"><span data-stu-id="362ab-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="362ab-106">**X non** utilizzare parole chiave specifiche della lingua dei linguaggi CLR principale.</span><span class="sxs-lookup"><span data-stu-id="362ab-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="362ab-107">**✓ SI** utilizzare solo caratteri alfanumerici e caratteri di sottolineatura nei nomi delle risorse.</span><span class="sxs-lookup"><span data-stu-id="362ab-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="362ab-108">**✓ SI** utilizzare la seguente convenzione di denominazione per le risorse di messaggio di eccezione.</span><span class="sxs-lookup"><span data-stu-id="362ab-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="362ab-109">L'identificatore di risorsa deve essere il nome del tipo di eccezione e un identificatore breve dell'eccezione:</span><span class="sxs-lookup"><span data-stu-id="362ab-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="362ab-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="362ab-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="362ab-111">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="362ab-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="362ab-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="362ab-112">See Also</span></span>  
 [<span data-ttu-id="362ab-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="362ab-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="362ab-114">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="362ab-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
