---
title: Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 149acc2baac0f45fa971a11f254d694526d140d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397324"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="e3130-102">Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione</span><span class="sxs-lookup"><span data-stu-id="e3130-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="e3130-103">Un punto (.) o punto esclamativo (!) che non si trova all'interno di un `With` blocco si verifica senza un'espressione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="e3130-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="e3130-104">L'accesso ai membri ( `.` ) e l'accesso ai membri del dizionario ( `!` ) richiedono un'espressione che specifica l'elemento che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="e3130-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="e3130-105">Deve essere visualizzato immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco contenente l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="e3130-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="e3130-106">**ID errore:** BC30157</span><span class="sxs-lookup"><span data-stu-id="e3130-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3130-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e3130-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e3130-108">Verificare che il `With` blocco sia formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e3130-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="e3130-109">Se non è presente alcun `With` blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito contenente il membro.</span><span class="sxs-lookup"><span data-stu-id="e3130-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3130-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3130-110">See also</span></span>

- [<span data-ttu-id="e3130-111">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="e3130-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="e3130-112">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="e3130-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
