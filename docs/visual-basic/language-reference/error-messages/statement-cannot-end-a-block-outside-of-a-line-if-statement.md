---
title: L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0e645ccf17d0aba702a576791622aa4e9b3dd5e0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593261"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="e714a-102">L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'</span><span class="sxs-lookup"><span data-stu-id="e714a-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="e714a-103">Una riga singola `If` istruzione contiene più istruzioni separate da punti (:), uno dei quali è un `End` istruzione per un blocco di controllo di fuori di riga singola `If`.</span><span class="sxs-lookup"><span data-stu-id="e714a-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="e714a-104">Riga singola `If` non usano le istruzioni di `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e714a-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="e714a-105">**ID errore:** BC32005</span><span class="sxs-lookup"><span data-stu-id="e714a-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e714a-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e714a-106">To correct this error</span></span>  
  
- <span data-ttu-id="e714a-107">Spostare il controllo a riga singola `If` istruzione all'esterno del blocco di controllo che contiene il `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e714a-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e714a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e714a-108">See also</span></span>

- [<span data-ttu-id="e714a-109">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="e714a-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
