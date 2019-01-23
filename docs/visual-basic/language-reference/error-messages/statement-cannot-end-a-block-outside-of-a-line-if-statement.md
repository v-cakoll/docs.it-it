---
title: L'istruzione non è possibile terminare un blocco all'esterno di una riga &#39;se&#39; istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574716"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>L'istruzione non è possibile terminare un blocco all'esterno di una riga &#39;se&#39; istruzione
Una riga singola `If` istruzione contiene più istruzioni separate da punti (:), uno dei quali è un `End` istruzione per un blocco di controllo di fuori di riga singola `If`. Riga singola `If` non usano le istruzioni di `End If` istruzione.  
  
 **ID errore:** BC32005  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il controllo a riga singola `If` istruzione all'esterno del blocco di controllo che contiene il `End If` istruzione.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
