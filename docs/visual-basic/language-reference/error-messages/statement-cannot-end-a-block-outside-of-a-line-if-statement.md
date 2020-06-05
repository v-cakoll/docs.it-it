---
title: L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400318"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="2757e-102">L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'</span><span class="sxs-lookup"><span data-stu-id="2757e-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="2757e-103">Un'istruzione a riga singola `If` contiene diverse istruzioni separate da due punti (:), una delle quali è un' `End` istruzione per un blocco di controllo all'esterno della riga singola `If` .</span><span class="sxs-lookup"><span data-stu-id="2757e-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="2757e-104">Per le istruzioni a riga singola `If` non viene utilizzata l' `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2757e-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="2757e-105">**ID errore:** BC32005</span><span class="sxs-lookup"><span data-stu-id="2757e-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2757e-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2757e-106">To correct this error</span></span>  
  
- <span data-ttu-id="2757e-107">Spostare l'istruzione a riga singola `If` all'esterno del blocco di controllo che contiene l' `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2757e-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2757e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2757e-108">See also</span></span>

- [<span data-ttu-id="2757e-109">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="2757e-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
