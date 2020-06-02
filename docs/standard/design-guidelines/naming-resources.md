---
title: Denominazione di risorse
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 762ba99c4751ba40f5f33e99455cf950af35cdf6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290149"
---
# <a name="naming-resources"></a><span data-ttu-id="9a54c-102">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="9a54c-102">Naming Resources</span></span>
<span data-ttu-id="9a54c-103">Poiché è possibile fare riferimento alle risorse localizzabili tramite determinati oggetti come se fossero proprietà, le linee guida per la denominazione delle risorse sono simili alle linee guida della proprietà.</span><span class="sxs-lookup"><span data-stu-id="9a54c-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="9a54c-104">✔️ utilizzare sistema Pascal nelle chiavi di risorsa.</span><span class="sxs-lookup"><span data-stu-id="9a54c-104">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="9a54c-105">✔️ forniscono identificatori descrittivi anziché brevi.</span><span class="sxs-lookup"><span data-stu-id="9a54c-105">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="9a54c-106">❌Non usare parole chiave specifiche del linguaggio dei linguaggi CLR principali.</span><span class="sxs-lookup"><span data-stu-id="9a54c-106">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="9a54c-107">✔️ utilizzano solo caratteri alfanumerici e caratteri di sottolineatura nelle risorse di denominazione.</span><span class="sxs-lookup"><span data-stu-id="9a54c-107">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="9a54c-108">✔️ utilizzare la convenzione di denominazione seguente per le risorse dei messaggi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="9a54c-108">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="9a54c-109">L'identificatore di risorsa deve essere il nome del tipo di eccezione più un identificatore breve dell'eccezione:</span><span class="sxs-lookup"><span data-stu-id="9a54c-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="9a54c-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="9a54c-110">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="9a54c-111">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="9a54c-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="9a54c-112">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="9a54c-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="9a54c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a54c-113">See also</span></span>

- [<span data-ttu-id="9a54c-114">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="9a54c-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="9a54c-115">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="9a54c-115">Naming Guidelines</span></span>](naming-guidelines.md)
