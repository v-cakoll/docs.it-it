---
title: "Interlinea &#39;. &#39; o &#39;! &#39; può trovarsi solo all'interno di un &#39; Con &#39; istruzione"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="dceb5-102">Interlinea &#39;. &#39; o &#39;! &#39; può trovarsi solo all'interno di un &#39; Con &#39; istruzione</span><span class="sxs-lookup"><span data-stu-id="dceb5-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="dceb5-103">Un punto (.) o un punto esclamativo (!) che non è all'interno un `With` blocco si verifica senza un'espressione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="dceb5-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="dceb5-104">Accesso ai membri (`.`) e accesso ai membri dizionario (`!`) richiedono un'espressione che specifica l'elemento che contiene il membro.</span><span class="sxs-lookup"><span data-stu-id="dceb5-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="dceb5-105">Questo deve apparire immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco che contiene l'accesso al membro.</span><span class="sxs-lookup"><span data-stu-id="dceb5-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="dceb5-106">**ID errore:** BC30157</span><span class="sxs-lookup"><span data-stu-id="dceb5-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dceb5-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="dceb5-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="dceb5-108">Verificare che il `With` blocco sia formattato correttamente.</span><span class="sxs-lookup"><span data-stu-id="dceb5-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="dceb5-109">Se è presente alcun `With` di blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito contenente il membro.</span><span class="sxs-lookup"><span data-stu-id="dceb5-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dceb5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dceb5-110">See Also</span></span>  
 [<span data-ttu-id="dceb5-111">Caratteri speciali nel codice</span><span class="sxs-lookup"><span data-stu-id="dceb5-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="dceb5-112">Istruzione With...End With</span><span class="sxs-lookup"><span data-stu-id="dceb5-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
