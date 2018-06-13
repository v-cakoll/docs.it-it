---
title: Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non è contrassegnato come &#39;personalizzata&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594499"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="28c5f-102">Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non è contrassegnato come &#39;personalizzata&#39;</span><span class="sxs-lookup"><span data-stu-id="28c5f-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="28c5f-103">Definizione di una struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.</span><span class="sxs-lookup"><span data-stu-id="28c5f-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="28c5f-104">Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (condiviso) anziché a tutte le istanze collettivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="28c5f-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="28c5f-105">Routine, proprietà e costanti non condivise non soddisfano questo requisito.</span><span class="sxs-lookup"><span data-stu-id="28c5f-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="28c5f-106">Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="28c5f-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="28c5f-107">**ID errore:** BC30941</span><span class="sxs-lookup"><span data-stu-id="28c5f-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="28c5f-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="28c5f-108">To correct this error</span></span>  
  
-   <span data-ttu-id="28c5f-109">Definire almeno una variabile o un evento che non `Shared`.</span><span class="sxs-lookup"><span data-stu-id="28c5f-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="28c5f-110">Se si definisce un solo evento, è necessario non personalizzati, nonché non condiviso.</span><span class="sxs-lookup"><span data-stu-id="28c5f-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c5f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28c5f-111">See Also</span></span>  
 [<span data-ttu-id="28c5f-112">Strutture</span><span class="sxs-lookup"><span data-stu-id="28c5f-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="28c5f-113">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="28c5f-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="28c5f-114">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="28c5f-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
