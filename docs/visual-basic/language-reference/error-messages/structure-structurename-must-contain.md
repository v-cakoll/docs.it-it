---
title: Struttura &#39; &lt;nomestruttura&gt;&#39; deve contenere una variabile membro di almeno un'istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39; Custom &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords: BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="c2404-102">Struttura &#39; &lt;nomestruttura&gt;&#39; deve contenere una variabile membro di almeno un'istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39; Custom &#39;</span><span class="sxs-lookup"><span data-stu-id="c2404-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="c2404-103">Definizione di una struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.</span><span class="sxs-lookup"><span data-stu-id="c2404-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="c2404-104">Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (condiviso) anziché a tutte le istanze collettivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="c2404-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="c2404-105">Routine, proprietà e costanti non condivise non soddisfano questo requisito.</span><span class="sxs-lookup"><span data-stu-id="c2404-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="c2404-106">Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="c2404-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="c2404-107">**ID errore:** BC30941</span><span class="sxs-lookup"><span data-stu-id="c2404-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2404-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c2404-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c2404-109">Definire almeno una variabile o un evento che non `Shared`.</span><span class="sxs-lookup"><span data-stu-id="c2404-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="c2404-110">Se si definisce un solo evento, è necessario non personalizzati, nonché non condiviso.</span><span class="sxs-lookup"><span data-stu-id="c2404-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2404-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2404-111">See Also</span></span>  
 [<span data-ttu-id="c2404-112">Strutture</span><span class="sxs-lookup"><span data-stu-id="c2404-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="c2404-113">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="c2404-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="c2404-114">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="c2404-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
