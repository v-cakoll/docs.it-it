---
title: Linee guida di progettazione delle eccezioni
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
ms.openlocfilehash: b64b6052aeb99c6e878c1a9aac50e67bca7f8d2a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709374"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="75294-102">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="75294-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="75294-103">La gestione delle eccezioni presenta molti vantaggi rispetto alla segnalazione degli errori basata sul valore restituito.</span><span class="sxs-lookup"><span data-stu-id="75294-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="75294-104">Una progettazione di Framework efficace consente allo sviluppatore di applicazioni di realizzare i vantaggi delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="75294-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="75294-105">In questa sezione vengono illustrati i vantaggi delle eccezioni e vengono presentate le linee guida per utilizzarle in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="75294-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75294-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="75294-106">In This Section</span></span>  
 [<span data-ttu-id="75294-107">Generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="75294-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="75294-108">Uso di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="75294-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="75294-109">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="75294-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="75294-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="75294-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="75294-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="75294-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75294-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75294-112">See also</span></span>

- [<span data-ttu-id="75294-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="75294-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
