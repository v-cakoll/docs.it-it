---
title: Istruzione non può terminare con un blocco all'esterno di una riga &#39;se&#39; istruzione
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>Istruzione non può terminare con un blocco all'esterno di una riga &#39;se&#39; istruzione
Una riga singola `If` istruzione contiene più istruzioni separate da punti (:), di cui uno è un `End` istruzione per un blocco di controllo esterno a riga singola `If`. Riga singola `If` istruzioni non utilizzano il `End If` istruzione.  
  
 **ID errore:** BC32005  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il controllo a riga singola `If` istruzione all'esterno del blocco di controllo che contiene il `End If` istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
