---
title: L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055134"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="23e1c-102">L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'</span><span class="sxs-lookup"><span data-stu-id="23e1c-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="23e1c-103">Una riga singola `If` istruzione contiene più istruzioni separate da punti (:), uno dei quali è un `End` istruzione per un blocco di controllo di fuori di riga singola `If`.</span><span class="sxs-lookup"><span data-stu-id="23e1c-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="23e1c-104">Riga singola `If` non usano le istruzioni di `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="23e1c-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="23e1c-105">**ID errore:** BC32005</span><span class="sxs-lookup"><span data-stu-id="23e1c-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23e1c-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="23e1c-106">To correct this error</span></span>  
  
- <span data-ttu-id="23e1c-107">Spostare il controllo a riga singola `If` istruzione all'esterno del blocco di controllo che contiene il `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="23e1c-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e1c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23e1c-108">See also</span></span>

- [<span data-ttu-id="23e1c-109">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="23e1c-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
