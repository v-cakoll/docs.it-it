---
title: La struttura '<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 598aef3943a53ee6eb97064819c9128de1839f52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813938"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="c49f4-102">Struttura '\<nomestruttura >' deve contenere almeno una variabile membro di istanza o dichiarazione di evento almeno un'istanza non contrassegnata 'Custom'</span><span class="sxs-lookup"><span data-stu-id="c49f4-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>
<span data-ttu-id="c49f4-103">Una definizione di struttura non include eventuali variabili non condivise o eventi non personalizzati non condivisi.</span><span class="sxs-lookup"><span data-stu-id="c49f4-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="c49f4-104">Ogni struttura deve essere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condiviso](../../../visual-basic/language-reference/modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="c49f4-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)).</span></span> <span data-ttu-id="c49f4-105">Procedure, le proprietà e le costanti non condivise non soddisfano questo requisito.</span><span class="sxs-lookup"><span data-stu-id="c49f4-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="c49f4-106">Inoltre, se sono presenti un solo evento non condiviso e nessuna variabile non condivisa, tale evento non può essere un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="c49f4-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="c49f4-107">**ID errore:** BC30941</span><span class="sxs-lookup"><span data-stu-id="c49f4-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c49f4-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c49f4-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c49f4-109">Definire almeno una variabile o un evento che non è `Shared`.</span><span class="sxs-lookup"><span data-stu-id="c49f4-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="c49f4-110">Se si definisce un solo evento, deve essere non personalizzati, nonché non condivisa.</span><span class="sxs-lookup"><span data-stu-id="c49f4-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49f4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c49f4-111">See also</span></span>

- [<span data-ttu-id="c49f4-112">Strutture</span><span class="sxs-lookup"><span data-stu-id="c49f4-112">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c49f4-113">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="c49f4-113">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="c49f4-114">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="c49f4-114">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
