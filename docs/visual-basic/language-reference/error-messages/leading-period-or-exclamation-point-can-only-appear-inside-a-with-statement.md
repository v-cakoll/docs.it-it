---
title: Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 367da8e7c9fd8c14a16a09b1f023e7637d78309d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259552"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="815e5-102">Il carattere '.' o '!' iniziale può trovarsi solo all'interno di un'istruzione</span><span class="sxs-lookup"><span data-stu-id="815e5-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="815e5-103">Un punto (.) o un punto esclamativo (!) che non è compreso in un `With` blocchi si verifica senza un'espressione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="815e5-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="815e5-104">Accesso ai membri (`.`) e accesso ai membri dizionario (`!`) richiedono un'espressione che specifica l'elemento che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="815e5-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="815e5-105">Questo deve apparire immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco che contiene l'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="815e5-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="815e5-106">**ID errore:** BC30157</span><span class="sxs-lookup"><span data-stu-id="815e5-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="815e5-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="815e5-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="815e5-108">Verificare che il `With` blocco sia formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="815e5-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="815e5-109">Se è presente alcun `With` blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="815e5-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815e5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="815e5-110">See also</span></span>
- [<span data-ttu-id="815e5-111">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="815e5-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="815e5-112">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="815e5-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
