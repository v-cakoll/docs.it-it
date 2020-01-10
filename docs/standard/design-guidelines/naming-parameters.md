---
title: Denominazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709179"
---
# <a name="naming-parameters"></a><span data-ttu-id="982bb-102">Denominazione di parametri</span><span class="sxs-lookup"><span data-stu-id="982bb-102">Naming Parameters</span></span>
<span data-ttu-id="982bb-103">Oltre al motivo più ovvio della leggibilità, è importante seguire le linee guida per i nomi dei parametri, perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visivi forniscono funzionalità IntelliSense e di esplorazione delle classi.</span><span class="sxs-lookup"><span data-stu-id="982bb-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="982bb-104">**✓ DO** utilizzare Camel nei nomi di parametro.</span><span class="sxs-lookup"><span data-stu-id="982bb-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="982bb-105">**✓ DO** utilizzare nomi di parametro descrittivo.</span><span class="sxs-lookup"><span data-stu-id="982bb-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="982bb-106">**✓ CONSIDER** utilizzare nomi basati sul significato del parametro anziché il tipo del parametro.</span><span class="sxs-lookup"><span data-stu-id="982bb-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="982bb-107">Denominazione dei parametri di overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="982bb-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="982bb-108">**✓ DO** usare `left` e `right` per i nomi di parametro dell'operatore binario overload se è presente alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="982bb-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="982bb-109">**✓ DO** utilizzare `value` per unario overload degli operatori i nomi dei parametri se è presente alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="982bb-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="982bb-110">**✓ CONSIDER** nomi significativi per l'operatore di overload parametri se questo modo si aggiunge un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="982bb-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="982bb-111">**X DO NOT** le abbreviazioni di utilizzare uno o più indici numerici per l'operatore di overload i nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="982bb-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="982bb-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="982bb-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="982bb-113">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="982bb-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="982bb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="982bb-114">See also</span></span>

- [<span data-ttu-id="982bb-115">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="982bb-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="982bb-116">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="982bb-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
