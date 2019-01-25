---
title: Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39;personalizzata&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: d8c654c212a459d40c6cf20cd62c3e0fcda8511b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603781"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a><span data-ttu-id="1f0da-102">Struttura &#39; &lt;nomestruttura&gt; &#39; deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata &#39;personalizzata&#39;</span><span class="sxs-lookup"><span data-stu-id="1f0da-102">Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;</span></span>
<span data-ttu-id="1f0da-103">Una definizione di struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.</span><span class="sxs-lookup"><span data-stu-id="1f0da-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="1f0da-104">Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condiviso](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="1f0da-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="1f0da-105">Procedure, le proprietà e le costanti non condivise non soddisfano questo requisito.</span><span class="sxs-lookup"><span data-stu-id="1f0da-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="1f0da-106">Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="1f0da-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="1f0da-107">**ID errore:** BC30941</span><span class="sxs-lookup"><span data-stu-id="1f0da-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f0da-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1f0da-108">To correct this error</span></span>  
  
-   <span data-ttu-id="1f0da-109">Definire almeno una variabile o un evento che non è `Shared`.</span><span class="sxs-lookup"><span data-stu-id="1f0da-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="1f0da-110">Se si definisce un solo evento, deve essere non personalizzati, nonché non condivisa.</span><span class="sxs-lookup"><span data-stu-id="1f0da-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0da-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f0da-111">See also</span></span>
- [<span data-ttu-id="1f0da-112">Strutture</span><span class="sxs-lookup"><span data-stu-id="1f0da-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="1f0da-113">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="1f0da-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="1f0da-114">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="1f0da-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
