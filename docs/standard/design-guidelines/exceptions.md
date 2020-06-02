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
ms.openlocfilehash: d7580d4d3953b279824bba76b44c4134a7293b7a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289772"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="c86a7-102">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c86a7-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="c86a7-103">La gestione delle eccezioni presenta molti vantaggi rispetto alla segnalazione degli errori basata sul valore restituito.</span><span class="sxs-lookup"><span data-stu-id="c86a7-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="c86a7-104">Una progettazione di Framework efficace consente allo sviluppatore di applicazioni di realizzare i vantaggi delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c86a7-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="c86a7-105">In questa sezione vengono illustrati i vantaggi delle eccezioni e vengono presentate le linee guida per utilizzarle in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="c86a7-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c86a7-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c86a7-106">In This Section</span></span>  
 [<span data-ttu-id="c86a7-107">Generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="c86a7-107">Exception Throwing</span></span>](exception-throwing.md)  
 [<span data-ttu-id="c86a7-108">Uso di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="c86a7-108">Using Standard Exception Types</span></span>](using-standard-exception-types.md)  
 [<span data-ttu-id="c86a7-109">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="c86a7-109">Exceptions and Performance</span></span>](exceptions-and-performance.md)  
 <span data-ttu-id="c86a7-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c86a7-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c86a7-111">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c86a7-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86a7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c86a7-112">See also</span></span>

- [<span data-ttu-id="c86a7-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c86a7-113">Framework Design Guidelines</span></span>](index.md)
