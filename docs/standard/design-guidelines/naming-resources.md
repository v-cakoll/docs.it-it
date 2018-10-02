---
title: Denominazione di risorse
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034610"
---
# <a name="naming-resources"></a><span data-ttu-id="40120-102">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="40120-102">Naming Resources</span></span>
<span data-ttu-id="40120-103">Poiché possono fare riferimento a risorse localizzabili tramite determinati oggetti come se fossero proprietà, convenzioni di denominazione per le risorse sono simili alle linee guida per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="40120-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="40120-104">**✓ DO** utilizzare il sistema Pascal le chiavi di risorsa.</span><span class="sxs-lookup"><span data-stu-id="40120-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="40120-105">**✓ DO** forniscono descrittivo anziché identificatori breve.</span><span class="sxs-lookup"><span data-stu-id="40120-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="40120-106">**X DO NOT** utilizzare parole chiave specifiche della lingua dei linguaggi CLR principale.</span><span class="sxs-lookup"><span data-stu-id="40120-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="40120-107">**✓ DO** utilizzare solo caratteri alfanumerici e caratteri di sottolineatura nei nomi delle risorse.</span><span class="sxs-lookup"><span data-stu-id="40120-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="40120-108">**✓ DO** utilizzare la seguente convenzione di denominazione per le risorse di messaggio eccezione.</span><span class="sxs-lookup"><span data-stu-id="40120-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="40120-109">L'identificatore della risorsa deve essere il nome del tipo di eccezione e un identificatore breve dell'eccezione:</span><span class="sxs-lookup"><span data-stu-id="40120-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="40120-110">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="40120-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="40120-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="40120-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40120-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40120-112">See also</span></span>

- [<span data-ttu-id="40120-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="40120-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="40120-114">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="40120-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
