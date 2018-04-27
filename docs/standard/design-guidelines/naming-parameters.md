---
title: Denominazione di parametri
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3e5dfe35fd4f2939898acee44764535c6de5fe9e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="naming-parameters"></a><span data-ttu-id="06b09-102">Denominazione di parametri</span><span class="sxs-lookup"><span data-stu-id="06b09-102">Naming Parameters</span></span>
<span data-ttu-id="06b09-103">Oltre il motivo evidente di migliorare la leggibilità, è importante seguire le linee guida per i nomi dei parametri perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visiva forniscono Intellisense e funzionalità di esplorazione di classe.</span><span class="sxs-lookup"><span data-stu-id="06b09-103">Beyond the obvious reason of readability, it is important to follow the guidelines for parameter names because parameters are displayed in documentation and in the designer when visual design tools provide Intellisense and class browsing functionality.</span></span>  
  
 <span data-ttu-id="06b09-104">**✓ SI** utilizzare Camel nei nomi di parametro.</span><span class="sxs-lookup"><span data-stu-id="06b09-104">**✓ DO** use camelCasing in parameter names.</span></span>  
  
 <span data-ttu-id="06b09-105">**✓ SI** utilizzare nomi di parametro descrittivo.</span><span class="sxs-lookup"><span data-stu-id="06b09-105">**✓ DO** use descriptive parameter names.</span></span>  
  
 <span data-ttu-id="06b09-106">**✓ Provare a** utilizzare nomi basati sul significato del parametro anziché il tipo del parametro.</span><span class="sxs-lookup"><span data-stu-id="06b09-106">**✓ CONSIDER** using names based on a parameter’s meaning rather than the parameter’s type.</span></span>  
  
### <a name="naming-operator-overload-parameters"></a><span data-ttu-id="06b09-107">Denominazione dei parametri di Overload di operatore</span><span class="sxs-lookup"><span data-stu-id="06b09-107">Naming Operator Overload Parameters</span></span>  
 <span data-ttu-id="06b09-108">**✓ SI** usare `left` e `right` per i nomi di parametro dell'operatore binario overload se è presente alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="06b09-108">**✓ DO** use `left` and `right` for binary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="06b09-109">**✓ SI** utilizzare `value` per unario overload degli operatori i nomi dei parametri se è presente alcun significato per i parametri.</span><span class="sxs-lookup"><span data-stu-id="06b09-109">**✓ DO** use `value` for unary operator overload parameter names if there is no meaning to the parameters.</span></span>  
  
 <span data-ttu-id="06b09-110">**✓ Provare a** nomi significativi per l'operatore di overload parametri se questo modo si aggiunge un valore significativo.</span><span class="sxs-lookup"><span data-stu-id="06b09-110">**✓ CONSIDER** meaningful names for operator overload parameters if doing so adds significant value.</span></span>  
  
 <span data-ttu-id="06b09-111">**X non** le abbreviazioni di utilizzare uno o più indici numerici per l'operatore di overload i nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="06b09-111">**X DO NOT** use abbreviations or numeric indices for operator overload parameter names.</span></span>  
  
 <span data-ttu-id="06b09-112">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="06b09-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="06b09-113">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="06b09-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b09-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06b09-114">See Also</span></span>  
 [<span data-ttu-id="06b09-115">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="06b09-115">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="06b09-116">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="06b09-116">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
