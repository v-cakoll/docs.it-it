---
title: La struttura '<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 7b5bda7b1a2ae37eb509c736deae1652dc5e6ab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374018"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a><span data-ttu-id="419f5-102">La struttura '\<structurename>' deve contenere almeno una dichiarazione di evento o di variabile membro di istanza non contrassegnata 'Custom'</span><span class="sxs-lookup"><span data-stu-id="419f5-102">Structure '\<structurename>' must contain at least one instance member variable or at least one instance event declaration not marked 'Custom'</span></span>
<span data-ttu-id="419f5-103">Una definizione di struttura non include variabili non condivise o eventi non personalizzati non condivisi.</span><span class="sxs-lookup"><span data-stu-id="419f5-103">A structure definition does not include any nonshared variables or nonshared noncustom events.</span></span>  
  
 <span data-ttu-id="419f5-104">Ogni struttura deve avere una variabile o un evento che si applica a ogni istanza specifica (non condivisa) invece che a tutte le istanze collettivamente ([condivise](../modifiers/shared.md)).</span><span class="sxs-lookup"><span data-stu-id="419f5-104">Every structure must have either a variable or an event that applies to each specific instance (nonshared) instead of to all instances collectively ([Shared](../modifiers/shared.md)).</span></span> <span data-ttu-id="419f5-105">Le costanti, le proprietà e le routine non condivisi non soddisfano questo requisito.</span><span class="sxs-lookup"><span data-stu-id="419f5-105">Nonshared constants, properties, and procedures do not satisfy this requirement.</span></span> <span data-ttu-id="419f5-106">Inoltre, se non sono presenti variabili non condivise e un solo evento non condiviso, l'evento non può essere un `Custom` evento.</span><span class="sxs-lookup"><span data-stu-id="419f5-106">In addition, if there are no nonshared variables and only one nonshared event, that event cannot be a `Custom` event.</span></span>  
  
 <span data-ttu-id="419f5-107">**ID errore:** BC30941</span><span class="sxs-lookup"><span data-stu-id="419f5-107">**Error ID:** BC30941</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="419f5-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="419f5-108">To correct this error</span></span>  
  
- <span data-ttu-id="419f5-109">Definire almeno una variabile o un evento diverso da `Shared` .</span><span class="sxs-lookup"><span data-stu-id="419f5-109">Define at least one variable or event that is not `Shared`.</span></span> <span data-ttu-id="419f5-110">Se si definisce un solo evento, deve essere non personalizzato e non condiviso.</span><span class="sxs-lookup"><span data-stu-id="419f5-110">If you define only one event, it must be noncustom as well as nonshared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419f5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="419f5-111">See also</span></span>

- [<span data-ttu-id="419f5-112">Strutture</span><span class="sxs-lookup"><span data-stu-id="419f5-112">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="419f5-113">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="419f5-113">How to: Declare a Structure</span></span>](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="419f5-114">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="419f5-114">Structure Statement</span></span>](../statements/structure-statement.md)
