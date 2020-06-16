---
title: Denominazione di risorse
description: Esaminare le linee guida per la denominazione delle risorse in .NET, che sono simili alle linee guida per la denominazione delle proprietà.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 765337bcf9fad4f9a8c9272a15b5c77d02770471
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768248"
---
# <a name="naming-resources"></a><span data-ttu-id="d8638-103">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="d8638-103">Naming Resources</span></span>
<span data-ttu-id="d8638-104">Poiché è possibile fare riferimento alle risorse localizzabili tramite determinati oggetti come se fossero proprietà, le linee guida per la denominazione delle risorse sono simili alle linee guida della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d8638-104">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>

 <span data-ttu-id="d8638-105">✔️ utilizzare sistema Pascal nelle chiavi di risorsa.</span><span class="sxs-lookup"><span data-stu-id="d8638-105">✔️ DO use PascalCasing in resource keys.</span></span>

 <span data-ttu-id="d8638-106">✔️ forniscono identificatori descrittivi anziché brevi.</span><span class="sxs-lookup"><span data-stu-id="d8638-106">✔️ DO provide descriptive rather than short identifiers.</span></span>

 <span data-ttu-id="d8638-107">❌Non usare parole chiave specifiche del linguaggio dei linguaggi CLR principali.</span><span class="sxs-lookup"><span data-stu-id="d8638-107">❌ DO NOT use language-specific keywords of the main CLR languages.</span></span>

 <span data-ttu-id="d8638-108">✔️ utilizzano solo caratteri alfanumerici e caratteri di sottolineatura nelle risorse di denominazione.</span><span class="sxs-lookup"><span data-stu-id="d8638-108">✔️ DO use only alphanumeric characters and underscores in naming resources.</span></span>

 <span data-ttu-id="d8638-109">✔️ utilizzare la convenzione di denominazione seguente per le risorse dei messaggi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="d8638-109">✔️ DO use the following naming convention for exception message resources.</span></span>

 <span data-ttu-id="d8638-110">L'identificatore di risorsa deve essere il nome del tipo di eccezione più un identificatore breve dell'eccezione:</span><span class="sxs-lookup"><span data-stu-id="d8638-110">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>

 <span data-ttu-id="d8638-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span><span class="sxs-lookup"><span data-stu-id="d8638-111">`ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`</span></span>
 `ArgumentExceptionFileNameIsMalformed`

 <span data-ttu-id="d8638-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d8638-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d8638-113">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d8638-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d8638-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8638-114">See also</span></span>

- [<span data-ttu-id="d8638-115">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d8638-115">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="d8638-116">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="d8638-116">Naming Guidelines</span></span>](naming-guidelines.md)
