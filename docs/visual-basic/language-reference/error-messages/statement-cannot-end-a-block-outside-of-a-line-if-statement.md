---
title: L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0cee52f0ca00395d93c469aae6498fd3793f1085
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266312"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="57e93-102">L'istruzione non può terminare con un blocco all'esterno di un'istruzione di riga 'If'</span><span class="sxs-lookup"><span data-stu-id="57e93-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="57e93-103">Una riga singola `If` istruzione contiene più istruzioni separate da punti (:), uno dei quali è un `End` istruzione per un blocco di controllo di fuori di riga singola `If`.</span><span class="sxs-lookup"><span data-stu-id="57e93-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="57e93-104">Riga singola `If` non usano le istruzioni di `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57e93-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="57e93-105">**ID errore:** BC32005</span><span class="sxs-lookup"><span data-stu-id="57e93-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57e93-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="57e93-106">To correct this error</span></span>  
  
-   <span data-ttu-id="57e93-107">Spostare il controllo a riga singola `If` istruzione all'esterno del blocco di controllo che contiene il `End If` istruzione.</span><span class="sxs-lookup"><span data-stu-id="57e93-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57e93-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57e93-108">See also</span></span>
- [<span data-ttu-id="57e93-109">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="57e93-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
