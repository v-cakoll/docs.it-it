---
title: Linee guida di progettazione delle eccezioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 471746242e7abe491148201103741fd00f4338cb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="9e743-102">Linee guida di progettazione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="9e743-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="9e743-103">Eccezioni presenta numerosi vantaggi rispetto alla segnalazione errori basato sul valore restituito.</span><span class="sxs-lookup"><span data-stu-id="9e743-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="9e743-104">Progettazione di framework valido consente lo sviluppatore di applicazioni i vantaggi delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9e743-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="9e743-105">In questa sezione vengono illustrati i vantaggi delle eccezioni e vengono fornite linee guida per il loro utilizzo in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="9e743-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e743-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9e743-106">In This Section</span></span>  
 [<span data-ttu-id="9e743-107">Generazione di eccezioni</span><span class="sxs-lookup"><span data-stu-id="9e743-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="9e743-108">Uso di tipi di eccezioni standard</span><span class="sxs-lookup"><span data-stu-id="9e743-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="9e743-109">Eccezioni e prestazioni</span><span class="sxs-lookup"><span data-stu-id="9e743-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="9e743-110">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="9e743-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9e743-111">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9e743-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e743-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e743-112">See Also</span></span>  
 [<span data-ttu-id="9e743-113">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="9e743-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
